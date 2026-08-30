<script>
  // import svelteLogo from './assets/svelte.svg'
  // import viteLogo from '/vite.svg'
  // import Counter from './lib/Counter.svelte'
  import ProjectTab from "./lib/project_tab.svelte";
  import projectsdata from "./project_json/project_tab.json";
  import {goto} from "@mateothegreat/svelte5-router";
  let leftText = "KEITH"
  let project_txt = "Projects"
  let abt_txt = "About"
  let resume_txt = "Resume"
  let intro_txt = "Hi, my name is Keith."
  let projects = projectsdata.projects;
  // function typeEffect(element, text, speed = 60) {
  //   return new Promise(resolve => {
  //     let i = 0, isTag = false;

  //     (function type() {
  //       element.innerHTML = text.slice(0, ++i) + `<span class="blinker"></span>`;
  //       const char = text.slice(i - 1);
  //       if (char === "<") isTag = true;
  //       if (char === ">") isTag = false;
  //       if (i === text.length) return resolve();

  //       if (isTag) return type();
  //       setTimeout(type, speed);
  //     })();
  //   });
  // }
  function scrollSmooth(element_name){
    const element = document.getElementById(element_name);
    let yOffset = -70;
    const y = element.getBoundingClientRect().top + window.pageYOffset + yOffset;
    window.scrollTo({top: y, behavior: 'smooth'});
      

  }


</script>

<header class="topbar">
  <div class="bar_content">
    <div class="left">{leftText}</div>
    <nav class="info-bar">
      <button class="about_btn"on:click={() => scrollSmooth('about')}>{abt_txt}</button>
      <button class="proj_btn"on:click={() => scrollSmooth('projects')}>{project_txt}</button>
      <button class="resume_btn" on:click={() => scrollSmooth('resume')}>{resume_txt}</button>
      <button class="contact_btn" on:click={() => scrollSmooth('connections')}>Connections</button>
      <button class="portfolio_btn"on:click={() => goto("/portfolio")}>Portfolio</button>
    </nav>
  </div>
</header>

<main>
  <div id="about" class="about_square">
    <div class="about_container">
      <h1 class="intro_head">{intro_txt}</h1>
    </div>
    <span class="intro_cap">ABOUT</span>
    <p class="intro_content">
      I'm a student currently attending the University of Southern California
      under the Computer Science Games program. I'm blessed to be able to 
      pursue a plethora of varying interests, such as Game Development, AI/ML and music. 
    </p>
    <p class="intro_disclaimer">
      disclaimer: Koda is simply a nickname and not to confuse with other trademarked entities
    </p>
  </div>

  <div id="projects" class= "projects_section">
    <h1 class="proj_head">Projects</h1>
    <div class="project_container">
      {#each projects as project}
        <ProjectTab proj_title={project.title} description={project.description} image={project.image}/>
      {/each}
    </div>
  </div>

  <div id="resume" class= "resume_section">
    <h1 class="resume_head"> Resume</h1>
    <a href="src/assets/Resume.png" download>
      <img class="resume_pdf" src="src/assets/Resume.png" alt="My Resume"/>
    </a>
  </div>

  <div id="connections" class= "contact_section">
    <h1 class="contact_head"> Connections</h1>
    <div class="contact_container">
      <a href="https://github.com/KodaIsshin" target="_blank" rel="noreferrer">
        <img class="github_img" src="src/assets/github_logo.png" alt="GitHub" />
      </a>
      <a href="https://www.linkedin.com/in/keith-natakusuma-79785b2b8/">
        <img class="linkedin_img" src="src/assets/linkedin_logo.png" alt="LinkedIn" />
      </a>
    </div>
  </div>
</main>

<style>
  main{
    display: flex;
    flex-direction: column;
    padding-top: 70px;
    gap: 30px;
    align-items: center;
  }
  .projects_section{
    justify-content: center;
    padding: 10px 30px;
    display: grid;
  }
  .proj_head, .contact_head, .resume_head{
    font-family: FivoSans;
    font-weight: bold;
    font-style: oblique;
  }
  .contact_head{
    margin: 0 0 0 0;
  }
  .proj_head{
    margin-top: 0;
    margin-bottom: 3px;
    align-self: center;
    
  }
  .resume_head{
    align-self: left;
    float: left;
    display: flex;
    margin: 15px 0 25px;

  }

  .resume_pdf{
    height:900px;
    width: 700px;
    align-self: center;
    display: flex;
  }
  .resume_section{
    position: sticky;
    display: flex;
    flex-direction: column;
  }
  .topbar {
    position: fixed;
    display: flex;
    top: 0;
    left: 0;
    right: 0;
    height: 55px;
    background: #fffcfc00;
    color: white;
    backdrop-filter: blur(10px);
    border-bottom: 1px solid #8d8c8c1f;
    padding: 0 6vw;
    z-index: 9999;
  }
  .project_container{
    position: relative;
    display: grid;
    gap: 15px;
    flex-wrap: wrap;
    grid-template-columns: repeat(3, 1fr);
    grid-auto-rows: auto;
    justify-content: center;
    align-self: center; 
  }

  .info-bar {
    display: flex;
    align-items: center;
    gap: clamp(0.5rem, 2vw, 1rem);
    margin-bottom: .5vw;
  }

  .bar_content {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
  }

  .left{
    font-size: clamp(2rem, 1.75vw, 2.5em);
    font-weight: bold;
    color: #ffffff;
    margin-right: 2vw;
    font-family: Tarawera;
  }
  .about_square{
    position: sticky;
    background: #101010;
    height: 40%;
    width: 70%;
    display: flex;
    flex-direction: column;
    border-radius: 16px;
    border: 4px solid #191919;
    padding-right: 10px;
    align-self: center;
  }
  .proj_btn, .about_btn, .resume_btn, .contact_btn, .portfolio_btn{
    border: 4;
    padding:8px 15px;
    text-align: center;
    background-color: #ffffff;
    color: #000000;
    border-radius: 8px;
    transition: 250ms linear 50ms;
    font-family: Sunshine LB;
  }
  .proj_btn:hover, .about_btn:hover, .resume_btn:hover, .contact_btn:hover, .portfolio_btn:hover{
    border-color: #00a4ea;
    background-color: #0b0146d9;
    color: #fffefe;
  }
  .intro_head{
    margin-left:30px;
    margin-top: 15px;
    font-size: 3.8vw;
    font-family: FivoSans;
    font-style: oblique;
    font-style: bold;
    align-self: start;
    display:flex;
    
  }
  .intro_cap{
    display: flex;
    margin-left: 35px;
    font-size: 1.8vw;
    font-family: Code-New-Roman;
    font-weight: bold;
    color: rgba(255, 255, 255, 0.281)
  }

  .intro_content{
    display: flex;
    font-family: Sunshine LB;
    text-align: left;
    margin-left: 35px;
    max-width: 60ch;
    font-size: 1.5vw;
  }

  .intro_disclaimer{
    display:flex;
    margin-left: 35px;
    font-size: .85vw;
    font-family: Sunshine LB;
    color: #8f8f8f50
  }

  .contact_container{
    margin-top: 15px;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 35px;
  }

  .github_img, .linkedin_img{
    height: 50px;
    width: 50px;
    transition: 0.3s ease-in-out;
    will-change: filter;
    border-radius: 8px;
    transition: ease-in-out 0.3s;
  }

  .github_img:hover{
    filter: drop-shadow(0 0 15px #ffffffaa);
    cursor: pointer;
  }

  .linkedin_img:hover{
    filter: drop-shadow(0 0 15px #0e76a8aa);
    cursor: pointer;
  }



</style>
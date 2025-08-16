<script>
  // import svelteLogo from './assets/svelte.svg'
  // import viteLogo from '/vite.svg'
  // import Counter from './lib/Counter.svelte'
  let leftText = "KODA"
  let project_txt = "Projects"
  let abt_txt = "About"
  let resume_txt = "Resume"
  let intro_txt = "Hi, my name is Keith."

</script>

<head>
  <title>Keith's Portfolio</title>
</head>

<header class="topbar">
  <div class="bar_content">
    <div class="left">{leftText}</div>
    <nav class="info-bar">
      <button class="about_btn">{abt_txt}</button>
      <button class="proj_btn">{project_txt}</button>
      <button class="resume_btn">{resume_txt}</button>
      <button class="contact_btn">Contact</button>
    </nav>
  </div>
</header>

<main>
  <div class="about_square">
    <h1 class="intro_head">{intro_txt}</h1>
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

  <div class= "projects_section">
    <h1 class="proj_head">Projects</h1>
  </div>

  <div class= "resume_section">
    <h1 class="resume_head"> Resume</h1>
  </div>

  <div class= "contact_section">
    <h1 class="contact_head"> Contact</h1>
  </div>
</main>

<style>
  .projects_section{
    position: sticky;
    display: flex;
    padding: 10px 30px;
    flex-direction: column;
    
  }
  .proj_head, .contact_head, .resume_head{
    font-family: FivoSans;
    font-weight: bold;
    font-style: oblique;
    font-size: 4vw;
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
    height: 25vw;
    width: 70vw;  
    display: flex;
    flex-direction: column;
    border-radius: 16px;
    margin-top: 45px;
    border: 4px solid #191919;
  }
  .proj_btn, .about_btn, .resume_btn, .contact_btn{
    border: 4;
    padding:8px 15px;
    text-align: center;
    background-color: #ffffff;
    color: #000000;
    border-radius: 8px;
    transition: 250ms linear 50ms;
    font-family: Sunshine LB;
  }
  .proj_btn:hover, .about_btn:hover, .resume_btn:hover, .contact_btn:hover{
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

</style>

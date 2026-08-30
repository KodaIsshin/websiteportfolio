<script>
 import {goto} from "@mateothegreat/svelte5-router";
 import {onMount} from "svelte";
 import current_characterfront from "../assets/images/games/Unarmed/current_model_front.png";
 import current_characterback from "../assets/images/games/Unarmed/current_model_back.png";
 import current_characterside from "../assets/images/games/Unarmed/current_model_side.png";
 import pistol_side1 from "../assets/images/games/Unarmed/pistol_side1.png";
 import pistol_side2 from "../assets/images/games/Unarmed/pistol_side2.png";
 import lever_action from "../assets/images/games/Unarmed/lever_action_shotgun.png";
 import Logo from "../assets/images/games/Unarmed/Logo Editable.jpg";
 import combatDisplay from "../assets/images/games/Unarmed/Combat display.jpeg"
 import ConceptualCity from "../assets/images/games/Unarmed/Conceptual city design.jpeg"
 import character_protoype_f from "../assets/images/games/Unarmed/character_prototype_front.png";
 import character_protoype_back from "../assets/images/games/Unarmed/character_prototype_back.png";
 import character_protoype_side from "../assets/images/games/Unarmed/character_prototype_side.png";
 import character_prototype from "../assets/images/games/Unarmed/player_character_prototype.jpeg";
 import dialogue_showcase from "../assets/images/games/Unarmed/Dialogue Showcase.jpeg";
 import MidRunShop from "../assets/images/games/Unarmed/Mid Run Shop.jpeg";
 import pistol_proto from "../assets/images/games/Unarmed/Pistol_protoype.jpeg"
 import RiggingDoc1 from "../assets/images/games/Unarmed/Rigging_Doc_1.png"
 import RiggingDoc2 from "../assets/images/games/Unarmed/Rigging_Doc_2.png"
 import RiggingDoc3 from "../assets/images/games/Unarmed/Rigging_Doc_3.png"
 import RiggingDoc4 from "../assets/images/games/Unarmed/Rigging_Doc_4.png"
 import RiggingDoc5 from "../assets/images/games/Unarmed/Rigging_Doc_5.png"
 import RiggingDoc6 from "../assets/images/games/Unarmed/Rigging_Doc_6.png"
 import RiggingDoc7 from "../assets/images/games/Unarmed/Rigging_Doc_7.png"
 import HeadLogo from "../assets/images/games/Unarmed/Head Logo.png"
 import SimpleAim from "../assets/images/games/Simple/Simple Aim.png"
 import SimpleCatch from "../assets/images/games/Simple/Simple Catch.png"
 import SimpleDodge from "../assets/images/games/Simple/Simple Dodge.png"
 import SimpleJump from "../assets/images/games/Simple/Simple Jump.png"
 import SimpleMatch1 from "../assets/images/games/Simple/Simple Match 1.png"
 import SimpleMatch2 from "../assets/images/games/Simple/Simple Match 2.png"
 import SimpleMaze from "../assets/images/games/Simple/Simple Maze.png"
 import SimpleMenu from "../assets/images/games/Simple/Simple Menu.png"
 import SimpleRhythm from "../assets/images/games/Simple/Simple Rhythm.png"
 import BossAsset from "../assets/images/games/Bullet Spread/Boss Asset copy.png"
 import ButterflyDemon from "../assets/images/games/Bullet Spread/Butterfly Demon copy.png"
 import Grave from "../assets/images/games/Bullet Spread/Grave copy.png"
 import HeartIcon1 from "../assets/images/games/Bullet Spread/Heart Icon-1 copy.png"
 import HeartIcon2 from "../assets/images/games/Bullet Spread/Heart Icon-2 copy.png"
 import HeartIcon3 from "../assets/images/games/Bullet Spread/Heart Icon-3 copy.png"
 import HeartIcon4 from "../assets/images/games/Bullet Spread/Heart Icon-4 copy.png"
 import HeartIcon5 from "../assets/images/games/Bullet Spread/Heart Icon-5 copy.png"
 import Pistol from "../assets/images/games/Bullet Spread/Pistol_gun-1 copy.png"

 let leftText = "KEITH"
 let portfolio_idx = 0;
 let portfolio_length = 4;
 function prev(){
    portfolio_idx = (portfolio_idx - 1 + portfolio_length) % portfolio_length;
 }

 function next(){
    portfolio_idx = (portfolio_idx + 1) % portfolio_length;
 }

</script>

<header class="topbar">
    <div class="bar_content">
        <div class="left">{leftText}</div>
        <nav class="info-bar">
            <button class="home_btn"on:click={() => goto("")}>Home</button>
        </nav>
    </div>
</header>

<main>
    <h1 class="portfolio_header">Games Portfolio</h1>

    <div class="portfolio_div">
        <div class="button_nav">
            <button class="arrow_button" on:click={() =>{
                prev();
            }}>←</button>
                    <button class="arrow_button" on:click={() =>{
                next();
            }}>→</button>
        </div>
        <div class="portfolio_container">
            {#if portfolio_idx == 0}
                <h1 class="game_header">UNARMED</h1>
                <img class="unarmed_img" src="src/assets/images/games/Unarmed/Logo Editable.jpg" alt="Unarmed Logo"/>
                <p class="unarmed_desc">
                    UNARMED is a fast-paced 3D FPS where you play and amnesiac lab escapee returning to the dystopia you barely survived. Guided by 
                    an AI whose motives you don't trust, running through a society willfully blind to the corruption at its outskirts to find answers and eliminate the Monolith. 
                    <br/>
                    <br/>
                    Built in collaboration with partner Bradyn Cabianca as a from-scratch learning project, this game has been integral to my growth as a indie game dev.
                    Covering all fields of technical and creative game dev fields, I've touched 3D design, engineering, promotional design, animation, QA, etc.
                    We hope to target a Steam release in the near future. Below are my contributions.
                </p>
                <div class="unarmed_gameplay">
                    <h1 style="align-text: left;"class="gameplay_header">Gameplay Engineering</h1>
                    <div class="gameplay_container">
                        
                    </div>
                    <h2 style="font-family: FivoSans; margin-bottom: 0;" class="gameplay_contributions_header">Contributions</h2>
                    <ul class = "gameplay_list" style="margin-top: 0; margin-bottom: 0;">
                        <li>Implemented movement and gunplay systems, including current weapon types: Pistol, Shotgun, and Automatic Rifle.</li>
                        <li>Implemented the teleportation system, teleporting the player to a designated object, either with or without momentum, based on type.</li>
                        <li>Implemented the wave level system, where the player must clear all spawners and enemies in a level with a max enemy capacity before advancing.</li>
                        <li>Designed and implemented Perk Upgrade system, where players are able to spend in-run currency on randomized upgrades between runs. (Example: Shotgun Jump that propels the player opposite the direction they are facing.)</li>
                        <li>Implemented the currency system: enemies drop "orbs" that home in and accelerate towards the player. They both heal and grant currency. System was inspired by both the currency vacuum from Sekiro and Blood Echoes system from Bloodborne.</li>
                        <li>Implemented the dialogue system between the player and barter NPCs, delivering narrative context and exposition.</li>
                        <li>Implemented UI logic for the player; displaying health, live currency, and ammo.</li>
                        <li>Implemented weapon-throwing mechanics, with throw damage on enemy hit, and a automatic pickup system for nearby weapons on the ground.</li>
                        <li>Implemented Parrying and Melee combat systems.</li>
                    </ul>
                </div>
                <div class="unarmed_design">
                    <h1 style="align-text: left; margin-bottom: 0;" class="design_header">Design & Animation</h1>
                    <h2 style="font-family: FivoSans; margin-bottom: 0;" class="three-d_design_header">3D Design</h2>
                        <div class="three-d_container">
                            <img src={current_characterfront} alt="current_character_front"/>
                            <img src={current_characterback} alt="current_character_back"/>
                            <img src={current_characterside} alt="current_character_side"/>
                            <img src={pistol_side1} alt="pistol_side1"/>
                            <img src={pistol_side2} alt="pistol_side2"/>
                            <img src={lever_action} alt="lever_action"/>
                        </div>
                    <h2 style="font-family: FivoSans; margin-bottom: 0;" class="three-d_design_header">3D Animation</h2>
                    <div class="three-d_container">
                        <img src={current_characterfront} alt="current_character_front"/>
                        <img src={current_characterback} alt="current_character_back"/>
                        <img src={current_characterside} alt="current_character_side"/>
                        <img src={pistol_side1} alt="pistol_side1"/>
                        <img src={pistol_side2} alt="pistol_side2"/>
                        <img src={lever_action} alt="lever_action"/>
                    </div>
                    <h2 style="font-family: FivoSans; margin-bottom: 0;" class="two-d_design_header">2D Design</h2>
                    <div class="two-d_container">
                            <img src={Logo} alt="logo-banner.jpg"/>
                            <img src={HeadLogo} alt="head_logo.png"/>
                    </div>
                </div>
                <div class="unarmed documentation">
                    <h1 style="align-text: left;" class="design_header">Behind the Scenes</h1>
                    <div class="bts_container">
                        <img src={combatDisplay} alt="combat_display"/>
                        <img src={ConceptualCity} alt="city_concept"/>
                        <img src={character_protoype_f} alt="ch_proto_f"/>
                        <img src={character_protoype_back} alt="ch_proto_back"/>
                        <img src={character_protoype_side} alt="ch_proto_side"/>
                        <img src={character_prototype} alt="character_proto"/>
                        <img src={dialogue_showcase} alt="dialogue_showcase"/>
                        <img src={MidRunShop} alt="midrunshop"/>
                        <img src={pistol_proto} alt="pistol_proto"/>
                        <img src={RiggingDoc1} alt="rig_doc1"/>
                        <img src={RiggingDoc2} alt="rig_doc2"/>
                        <img src={RiggingDoc3} alt="rig_doc3"/>
                        <img src={RiggingDoc4} alt="rig_doc4"/>
                        <img src={RiggingDoc5} alt="rig_doc5"/>
                        <img src={RiggingDoc6} alt="rig_doc6"/>
                        <img src={RiggingDoc7} alt="rig_doc7"/>
                    </div>
                </div>
                <p>
                    
                </p>
            {:else if portfolio_idx == 1}
                <h1 class="game_header">
                    <a href="https://berserkerbray.itch.io/bullet-spread" target="_blank" rel="noreferrer">BULLET SPREAD</a>
                </h1>
                <img class="unarmed_img" src="src/assets/images/games/Unarmed/Logo Editable.jpg" alt="Unarmed Logo"/>
                <p class="unarmed_desc">
                    Bullet Spread is a metroidvania project built for a game jam for duos. This game was created within a 2 week period given the constraints of going along the theme of "It's spreading".
                    <br/>
                    <br/>
                    This game jam was a learning process for thinking quickly on ideas and making sure our ideas got to production, development, and release quickly and on deadline. As opposed to Unarmed, this game was integral to the hard skills of management that game devs must have in order to properly work together.
                    Above is a link to the game on itch.io if you wish to play it.
                </p>
                <div class="unarmed_gameplay">
                    <h1 style="align-text: left;"class="gameplay_header">Gameplay Engineering</h1>
                    <div class="gameplay_container">
                        
                    </div>
                    <h2 style="font-family: FivoSans; margin-bottom: 0;" class="gameplay_contributions_header">Contributions</h2>
                </div>
                <div class="unarmed_design">
                    <h2 style="font-family: FivoSans; margin-bottom: 0;" class="two-d_design_header">2D Design</h2>
                    <div class="two-d_container">
                            <img src={Logo} alt="logo-banner.jpg"/>
                            <img src={HeadLogo} alt="head_logo.png"/>
                    </div>
                </div>
                <p>
                    
                </p>
            {:else if portfolio_idx == 2}
                <h1 class="game_header">
                    <a href="https://drive.google.com/drive/u/2/folders/1bevZsCyM7nNEiaNlIixahZPYSxuG_zpd" target="_blank" rel="noreferrer">SIMPLE</a>
                </h1>
                <p class="unarmed_desc">
                    SIMPLE is a solo game project I developed to assist people with cognitive deficiencies improve in certain cognitive aspects such as coordination, rhythm, situation assessment, and memory.
                    <br/>
                    <br/>
                    SIMPLE was an experience that allowed me to go and study the psychological effect and benefit of simple games in order to stimulate the brains and give access to people who are unable to play more complex ones.
                    This game allowed me to study the appeal of retro sounds to spur engagement, building off of user feedback with a direct tester, and designing with a target audience in mind. The link in the header will direct you
                    to a google drive that has documentation of the game modes and testing.
                </p>
                <div class="unarmed_gameplay">
                    <h1 style="align-text: left;"class="gameplay_header">Gameplay Engineering</h1>
                    <div class="gameplay_container">
                        
                    </div>
                </div>
                <div class="unarmed_design">
                    <h2 style="font-family: FivoSans; margin-bottom: 0;" class="two-d_design_header">2D Design</h2>
                    <div class="two-d_container">
                        <img src={SimpleMenu} alt="simple_menu.png"/>
                        <img src={SimpleAim} alt="simple_aim.png"/>
                        <img src={SimpleCatch} alt="simple_catch.png"/>
                        <img src={SimpleDodge} alt="simple_dodge.png"/>
                        <img src={SimpleJump} alt="simple_jump.png"/>
                        <img src={SimpleMatch1} alt="simple_match1.png"/>
                        <img src={SimpleMatch2} alt="simple_Match2.png"/>
                        <img src={SimpleMaze} alt="simple_maze.png"/>
                        <img src={SimpleRhythm} alt="simple_rhythm.png"/>
                    </div>
                </div>
                <p>
                    
                </p>
            {:else if portfolio_idx == 3}
                <h1 class="game_header">UNITY ENGINEERING</h1>
                <div class="unarmed_design">
                    <h1 style="align-text: left; margin-bottom: 0;" class="design_header">Basketball Prototype</h1>
                        <div class="three-d_container">

                        </div>
                </div>
                <div class="unarmed_design">
                    <h1 style="align-text: left; margin-bottom: 0;" class="design_header">Grappling Traversal Prototype</h1>
                        <div class="three-d_container">
                        </div>
                </div>

            {/if}

        </div>
        

    </div>
    


</main>

<style>


main{
    display: flex;
    flex-direction: column;
    min-height: 100vh;

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

.bar_content {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
}

.home_btn{
    border: 4;
    padding:8px 15px;
    text-align: center;
    background-color: #ffffff;
    color: #000000;
    border-radius: 8px;
    transition: 250ms linear 50ms;
    font-family: Sunshine LB;
}

.button_nav{
    margin-bottom: 10px;
    align-self: end;
}



.left{
    font-size: clamp(2rem, 1.75vw, 2.5em);
    font-weight: bold;
    color: #ffffff;
    margin-right: 2vw;
    font-family: Tarawera;
}

.info-bar {
    display: flex;
    align-items: center;
    gap: clamp(0.5rem, 2vw, 1rem);
    margin-bottom: .5vw;
}

.portfolio_header{
    text-align: left;
    font-family: FivoSans;
    align-self: start;
    padding: 0 3vw;
    margin-bottom: 0
}

.portfolio_div{
    display: flex;
    width: 100%;
    flex-direction: column;
    justify-content: space-between;
}

.portfolio_container{
    border: 4px solid #191919;
    border-radius: 16px;
    width: 90%;
    padding: 1% 2%;
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
    overflow: scroll;
    align-self: center;
    
}

div::-webkit-scrollbar{
    display:none;
}

h1{
font-family: FivoSans;
}

.unarmed_img{
    align-self: center;
    width: 50%
}

.game_header{
    margin-top: 5px;
}

p{
    font-family: Sunshine LB;
}

.unarmed_desc{
    margin-top: 0;
    padding: 0 5px;

}
.three-d_container{
    border: 2px solid #ffffff;
    width: 100%;
    height: 400px;
    display: flex;
    align-items: center;
    overflow-x: scroll;
    justify-content: flex-start;


}

.three-d_container img{
    object-fit: contain;
    max-width:100%;
    max-height: 100%;
    width: auto;
    height: auto;
    padding: 5px 5px;
    box-sizing: border-box;
}

.two-d_container{
    border: 2px solid #ffffff;
    width: 100%;
    height: 400px;
    display: flex;
    align-items: center;
    overflow-x: scroll;
    justify-content: flex-start;


}

.two-d_container img{
    object-fit: contain;
    max-width:100%;
    max-height: 100%;
    width: auto;
    height: auto;
    padding: 5px 5px;
    box-sizing: border-box;
}

.bts_container{
    border: 2px solid #ffffff;
    width: 100%;
    height: 400px;
    display: flex;
    align-items: center;
    overflow-x: scroll;
    justify-content: flex-start;


}

.bts_container img{
    object-fit: contain;
    max-width:100%;
    max-height: 100%;
    width: auto;
    height: auto;
    padding: 5px 5px;
    box-sizing: border-box;
}


.unarmed_gameplay{
    display: flex;
    flex-direction: column;
    width: 100%;
}


.gameplay_container{
    width: 100%;
    min-height: 300px;
    border: 2px solid #ffffff;
    align-self: center;
    overflow: scroll;
    display: flex;
    flex-direction: row;
}


li{
    font-family: Sunshine LB;
}


</style>
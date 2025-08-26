<script>
    import {tick} from "svelte";
    export let proj_title;
    export let description;
    export let image;

    let el;
    let expanded = false;
    let showDesc = false;

    async function toggleExpand() {
        const container = el.closest('.project_container');
        const first = el.getBoundingClientRect();
        const last = container.getBoundingClientRect();
        el.style.transition = "transform 0.1s ease-in-out";
        expanded = !expanded;
        await tick();

        const deltaX = last.left - first.left;
        const deltaY = last.top - first.top;
        const scaleX = (last.width / first.width) - 10;
        const scaleY = (last.height / first.height);

        el.style.transformOrigin = "top left";
        el.style.transform = `
            translate(${deltaX}px, ${deltaY}px)
            scale(${scaleX}, ${scaleY})
        `;

        requestAnimationFrame(() => {
            el.style.transform = "none";
            if (expanded) {
                el.style.position = "absolute";
                el.style.top = `${first.top - last.top}px`;
                el.style.left = `${first.left - last.left}px`;
                el.style.width = `${first.width}px`;
                el.style.height = `${first.height}px`;
                el.style.zIndex = "1500";
            } else {
                el.style.position = "";
                el.style.top = "";
                el.style.left = "";
                el.style.width = "";
                el.style.height = "";
                el.style.zIndex = "1001";
            }
        });

        el.addEventListener(
            "transitionend",
            () => {
                el.style.transition = "";
                if (expanded) {
                    // After transition, fill the container
                    el.style.top = "0";
                    el.style.left = "0";
                    el.style.width = "100%";
                    el.style.height = "100%";
                    el.style.transform = "none"
                }
                else{
                     el.style.position = "";
                    el.style.top = "";
                    el.style.left = "";
                    el.style.width = "";
                    el.style.height = "";
                    el.style.transform = "none"
                }
            },
            {once: true}
        );
        if (expanded) {
            setTimeout(() => {
                showDesc = true;
            }, 200); 
        } else {
            showDesc = false;
        }
    }
</script>

<button class="proj_tab {expanded ? 'expanded' : ''}" on:click={toggleExpand} bind:this={el}>
    <img class="proj_img" src={image} alt={description} style="width:100%; height:100%; object-fit: cover;"/>
    {#if showDesc}
        <div class="proj_description" style="position: absolute; top: 10%; left: 10%; color: white; z-index: 2000; width: 80%; text-align: center;">
            <h2 style="font-family: Tarawera; font-size: 2vw; margin-bottom: 20px;">{proj_title}</h2>
            <p style="font-family: Code-New-Roman; font-size: 1.5vw; font-weight:bold">{description}</p>
        </div>
    {/if}
    <div class="proj_title">
        <h2 class="title_txt">{proj_title}</h2>
    </div>


</button>

<style>
.proj_tab{
    all: unset;
    background: #101010;
    height: 20vw;
    width: 275px;  
    display: grid;
    border-radius: 16px;
    margin-top: 45px;
    border: 4px solid #191919;  
    transition: transform 0.3s ease-in-out, width 0.3s ease, height 0.3s ease, top 0.3s ease, left 0.3s ease;
    overflow: hidden;
    transform-origin: top left;
    z-index: 1000;
}
.proj_title{
    align-self: last baseline;
    background: #000000;
    border-bottom-left-radius: 16px;
    border-bottom-right-radius: 16px;
    border-top: 4px solid #191919;
    font-family: Tarawera;
    cursor: pointer;
    z-index: 1001;
}
.proj_img{
    transition: filter 0.3s ease-in-out;
}
.title_txt{
    transition: 0.2s ease-in-out 100ms;
}

.proj_title:hover .title_txt{
    cursor: pointer;
    text-shadow: #a217d0 0px 0 25px;
}

.proj_tab:hover{
    border: 4px solid #8f8f8f;

}
.proj_tab.expanded{
    inset: 0;
    margin: 0;
}
.proj_tab.expanded .proj_img{
    filter: blur(5px) brightness(30%);

}



</style>

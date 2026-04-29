<script>
    import Barchart from "$lib/components/barchart.svelte";
    import { onMount } from "svelte";

    
    
    onMount(() => {
        const animatedElements = document.querySelectorAll('#img, #text');
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('show');
                }
            });
        }, { threshold: 0.1 });
    
        animatedElements.forEach(el => observer.observe(el));
    
        return () => {
            animatedElements.forEach(el => observer.unobserve(el));
        };
    });
    
</script>

<div id="section3">
    <div id="img">
        <div id="chartContainer">
            <Barchart />
        </div>
        <div id="sotto"></div>
    </div>
    <div id="text">
        <h1>Pillars of the Indelible </h1>
        <p>The structural qualities we carve into our work to make every insight impossible to ignore and harder to forget.</p>
    </div>
</div>

<style>

    *{
        padding: 0;
        margin: 0;
    }   

    #section3{
        display: flex;
        align-items: center;
        justify-content: space-between; 
        width: 100%; 
        margin: 0 auto;
        padding: 160px 80px;
        height: 100vh;
        position: relative;
        max-width: 1512px;
        
    }

    #sotto{
        width: 600px;
        height: 311px;
        background-color: var(--color-bg-secondary);
        border-radius: var(--radius-md);
        box-shadow:  inset 3px 4px 4px 0px var(--color-neomorph-shadow);
        transform: perspective(800px) rotateY(-20deg) rotateX(60deg) rotateZ(43deg);
        position: absolute;
        top: 52%;
        z-index: -1;
        left: 5%;

    }

    #chartContainer{
        transform: perspective(800px) rotateY(-50deg) rotateZ(5deg) rotateX(-5deg);
        position: relative;
        
        
    }

    #img{
        position: absolute;
        right: 5%;
        top: 20%;
        opacity: 0;
        transition: opacity 1.5s ease-in-out 0.2s, top 1.5s ease-in-out 0.2s;
        scale: 1.1;
    }

    #img:global(.show){
        top: 10%;
        opacity: 1;
    }

    #text{
        text-align: left;
        width: 527px;
        transform: translateX(-10%);
        opacity: 0;
        transition: opacity 1.5s ease-in-out 1s, transform 1.5s ease-in-out 1s;
    }

    #text:global(.show){
        transform: translateX(0);
        opacity: 1;
    }
    #text p{
        font-size: 20px;
        color: var(--color-text-secondary);
    }

    @media(max-width: 768px){
        #section3{
            flex-direction: column;
            padding: 80px var(--spacing-24);
            gap: 250px;
            height: fit-content;
        }

        #text{
            text-align: center;
            width: 100%;
        }

        #img{
            position: relative;
            scale: 0.8;
            transform: translateY(10%);
        }

        #img:global(.show){
            transform: translateY(-10%);
        }

    
    }

    @media(max-width: 600px){
        #section3{
            gap: 150px;
            padding: 80px var(--spacing-24);
        }

        #img{
            scale: 0.6;
            transform: translateY(10%);
        }
        
         #img:global(.show){
            transform: translateY(-10%);
        }

        #text p{
            font-size: 16px;

    }

    #text h1{
        font-size: 40px;
    }
    }
</style>
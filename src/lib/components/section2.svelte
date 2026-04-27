<script>
    import Cards from "./cards.svelte";
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

<div id="section2">
    <div id="img">
        <div id="cardContainer">
            <div id="svgContainer">
                <svg width="540" height="254" viewBox="0 0 540 254" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M128.5 106C178 107 213 236 278 236C333.587 236 471.082 78.0328 509.741 32.2786C516.288 24.5303 520 20 520 20V236H278H21C21 236 23.6924 229.919 28.412 220.387C45.5981 185.679 89.665 105.215 128.5 106Z" fill="url(#paint0_linear_1_14)"/>
                <path d="M28.412 220.387C45.5981 185.679 89.665 105.215 128.5 106C178 107 213 236 278 236C333.587 236 471.082 78.0328 509.741 32.2786" stroke="#78AEFF" stroke-width="8" fill="none"/>
                <circle cx="20" cy="234" r="16" fill="#78AEFF"/>
                <circle cx="520" cy="20" r="16" fill="#78AEFF"/>
                <defs>
                <linearGradient id="paint0_linear_1_14" x1="270" y1="20" x2="270" y2="236" gradientUnits="userSpaceOnUse">
                <stop stop-color="#78AEFF"/>
                <stop offset="1" stop-color="#EEEEEE" stop-opacity="0"/>
                </linearGradient>
                </defs>
                </svg>
            </div>
        </div>
    </div>
    <div id="text">
        <h1>Defined by Precision</h1>
        <p>A breakdown of the core attributes chiseled into every analysis to ensure clarity, impact, and depth.</p>
    </div>
</div>

<style>

*{
    padding: 0;
    margin: 0;
}
    #section2{
        display: flex;
        align-items: center;
        justify-content: center;
        gap: var(--spacing-64);
        width: 100%;
        padding: 80px;
        background-color: var(--color-bg-primary);
        gap: 15px;
        height: 100vh;
        max-width: 1512px;
        position: relative;
    }

    #cardContainer{
        display: flex;
        align-items: center;
        justify-content: center;
        width: fit-content;
        height: fit-content;
        padding: 40px;
        background-color: var(--color-bg-secondary);
        border-radius: 16px;
        box-shadow: inset -3px -4px 4px 0px var(--color-neomorph-light),
        inset 3px 2px 4px 0px var(--color-neomorph-shadow);
        transform: perspective(1000px) rotateY(40deg);

    }
    #text{
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        justify-content: center;
        gap: var(--spacing-16);
        width: 540px;
        height: fit-content;
        transform: translateY(20%);
        opacity: 0;
        transition: opacity 1.5s ease-in-out 0.2s, transform 1.5s ease-in-out 0.2s;
    }

    #text:global(.show){
        transform: translateY(0);
        opacity: 1;
    }
    #img{
        position: relative;
        transform: translateX(-5%);
        transition: opacity 1.5s ease-in-out 1s, transform 1.5s ease-in-out 1s;
        opacity: 0;
    }

    #img:global(.show){
        transform: translateX(0);
        opacity: 1;
    }

    #svgContainer{
        width: fit-content;
        height: fit-content;
        background-color: var(--color-bg-secondary);
        box-shadow: -3px 4px 4px 0px var(--color-neomorph-shadow);
        padding: 24px;
        border-radius: 12px;
    }

    #text p{
        color: var(--color-text-secondary);
    }


    @media (max-width: 768px){
        #section2{
            flex-direction: column;
            padding: 160px var(--spacing-40);
            justify-content: center;
            align-items: center;
            gap: 80px;
            height: 100vh;
        }

        #text{
            align-items: center;
            text-align: center;
            width: 100%;
        }

        #cardContainer{
            transform: translateX(10%) perspective(1000px) rotateY(40deg);
            scale: 0.9;
        }
        
        #text h1{
            font-size: 56px;
        }
        #text p{
            font-size: 20px;
            color: var(--color-text-secondary);
        }

    }

    @media (max-width: 600px){
       
            #section2{
                padding: 80px var(--spacing-24);
                gap: 40px;
            }
            #cardContainer{
                transform: translateX(10%) perspective(1000px) rotateY(40deg);
                scale: 0.6;
            }

            #text h1{
                font-size: 40px;
            }

            #text p{
                font-size: 16px;
            }
    }
   
</style>



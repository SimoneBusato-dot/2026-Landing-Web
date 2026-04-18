

<script>
    import Buttons from "./buttons.svelte";
</script>

<div id="hero">
    <img id="light-img"src="/image-hero.png" alt="Embedded Data">
    <img id="dark-img" src="/image-hero-dark.png" alt="Embedded Data">

    <div id="title-cta">
        <div id="title">
           <h1>Embedded Data</h1>
           <p>The true value does not lie in the shapeless mass of information, but in the figure we extract through a process of deliberate subtraction and refinement.</p>
        </div>
        <div id="buttons">
            <Buttons variant="primary">Get Started</Buttons>
            <Buttons variant="secondary">About Us</Buttons>
        </div>
    </div>
    

</div>


<style>

    #hero {
        display: flex;
        align-items: flex-end; 
        justify-content: flex-start;
        width: 90vw;
        background-color: var(--color-bg-primary);
        height: 90vh;
        padding: 40px 80px 40px 80px;
        overflow: hidden;
        
         
    }

    #title-cta {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        gap: var(--spacing-48);
        
    }
    
    #title {
        display: flex;
        flex-direction: column;
        gap: 0.125rem;
        align-items: flex-start;
        justify-content: flex-end;
    }   

    #title h1 {
        font-family: var(--font-inter);
        font-weight: var(--font-weight-bold);
        font-size: 64px;
        background: linear-gradient(
      -60.39554116875058deg,
      var(--color-gradient-primary-start) 18.326%,
      var(--color-gradient-primary-end) 69.64%
        );
         -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        background-clip: text;
        margin: 0;
    }

    #title p {
        font-family: var(--font-inter);
        font-weight: var(--font-weight-regular);
        font-size: 1.25rem;
        color: var(--color-text-secondary);
        max-width: 700px;
        margin-top: 0;
    }

    #buttons {
        display: flex;
        gap: var(--spacing-24);
    }

    #hero img {
        width: 666px;
        height: auto;
        object-fit: contain;
        position: absolute;
        right: 0;
        
    }
    #light-img {
        display: block;
    }
    #dark-img {
        display: none;
    }
    
    @media (prefers-color-scheme: dark) {
        #dark-img {
            display: block;
        }
        #light-img {
            display: none;
        }
    }


    @media (max-width: 768px) {
        #hero {
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 40px;
            height: fit-content;
            gap: var(--spacing-40);
            width: 100vw;
        }

        #title-cta {
            gap: var(--spacing-24);
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
        }

        #title h1 {
            font-size: 64px;
            text-align: center;
            width: 100%;
        }

        #title p {
            font-size: 20px;
            width: 617px;
        }

 

        #hero img {
            position: relative;
            width: 640px;
            
        }
    }

    @media (max-width: 600px){

        #title h1 {
            font-size: 40px;
        }
        #title p {
            width: 100%;
            font-size: var(--text-base);
        }

        #hero img {
            width: 100%;
        }
    }
</style>
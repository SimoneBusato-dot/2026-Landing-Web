<script>
    import Link from "./link.svelte";
   
    let isMenuOpen = $state(false);

   function toggleMenu() {
        const linkContainer = document.getElementById('link-container');
        const hamburger = document.getElementById('hamburger');
        const cross = document.getElementById('cross');
 
        isMenuOpen = !isMenuOpen;

        if (!isMenuOpen) {
            linkContainer.classList.remove('open');
            hamburger.style.opacity = '1';
            cross.style.opacity = '0';
        } else {
            linkContainer.classList.add('open');
            hamburger.style.opacity = '0';
            cross.style.opacity = '1';
        }
   }
</script>
<div id="nav-container">
    <nav>
        <p id="Logo">ED</p>
    
        <button id="svg-container" onclick={toggleMenu}>
        <svg id="hamburger"  width="21" height="16" viewBox="0 0 21 16" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M1 14.3333H19.6667M1 7.66667H19.6667M1 1H19.6667" stroke="#2C2C2C" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
        <svg id="cross"  width="13" height="13" viewBox="0 0 13 13" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M11.6666 11.6666L6.33335 6.33335M6.33335 6.33335L1 1M6.33335 6.33335L11.6667 1M6.33335 6.33335L1 11.6667" stroke="#2C2C2C" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
       </button>

        <div id="link-container" class:open={isMenuOpen}>
            <Link variant="active">Home</Link>
            <Link variant="default">About us</Link>
            <Link variant="default">Contacts</Link>
        </div>
    </nav>
</div>

<style>

    *{
        margin: 0;
        padding: 0;
    }

   

    #nav-container {
        display: flex;
        justify-content: center;
        width: 100%;
        height: fit-content;
        position: sticky;
        top: 6%;
        z-index: 100;
    }

    nav {
        display: flex;
        align-items: center;
        justify-content: space-between;
        width: 1352px;
        padding: 10px var(--spacing-32);
        background-color: var(--color-bg-primary);;
        border-radius: var(--radius-full);
        box-shadow: -6px -5px 4px 0px var(--color-neomorph-light), 3px 4px 4px 0px var(--color-neomorph-shadow);
        
        
        
    }

    #Logo {
        font-family: var(--font-inter);
        font-weight: var(--font-weight-bold);
        font-size: 24px;
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

    #link-container {
        display: flex;
        gap: var(--spacing-16);
    }

    #svg-container {
    /* Rimuovi stili di default del button se necessario */
   
    background-color: var(--color-bg-primary);    
    border: none;
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 44px; 
    height: 44px; 
    display: none;
}

svg path{
    stroke: var(--color-text-primary);
}

#hamburger, #cross {
    /* Entrambi sovrapposti al centro */
    position: absolute;
    transition: opacity 0.3s ease, transform 0.3s ease;
    
}

/* Stato iniziale: decidi cosa mostrare */
#hamburger {
    opacity: 1;
}

#cross {
    opacity: 0;
    
    
}

    @media (max-width: 768px) {
        #nav-container {
            width: 100vw;
            padding: var(--spacing-40);
        }
            nav {
                width: 664px;
                padding: 10px var(--spacing-32);
                height: fit-content;
            }

      
    }

    @media(max-width: 600px){
        #nav-container {
        top: auto; 
        position: fixed; 
        bottom: 5%;
        width: 100%;
        left: 0;
        padding: 0; 
        display: flex;
        flex-direction: column;
        align-items: center;
    }
        nav{
            width: 354px;
            padding: 10px var(--spacing-32);
            height: 52px;
            
        }



    #link-container {
        position: absolute; 
        flex-direction: column;
        background-color: var(--color-bg-primary);
        box-shadow: -6px -5px 4px 0px var(--color-neomorph-light), 3px 4px 4px 0px var(--color-neomorph-shadow);
        width: 354px;
        justify-content: center;
        align-items: center;
        border-radius: var(--radius-lg);
        z-index: -1;
        left: 50%;
        transform: translateX(-50%);
        bottom: 40px; 
        opacity: 0;
        height: 0;
        pointer-events: none;
        transition: all 0.2s ease;
       
    }
 
    #link-container.open {
        opacity: 1;
        pointer-events: all;
        height: fit-content;
        padding: var(--spacing-32);
    }

    
    #svg-container {
        opacity: 1;
        display: flex; 
        z-index: 1000;
    }
}
      

        

</style>
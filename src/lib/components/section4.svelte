<script>
    import Cards from "./cards.svelte";
</script>

<div id="section4">
    <div id="textcontainer">
        <h1>Our Approach</h1>
        <p>Examining the sculpted traits that transform raw data into an unforgettable masterpiece</p>
    </div>
    <div id="cardcontainer">
        <Cards variant="inner">
            <svg class="card-svg" width="151" height="151" viewBox="0 0 151 151" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M98 60.0833L67.6667 90.4167L52.5 75.25M75.25 143.5C37.5566 143.5 7 112.943 7 75.25C7 37.5566 37.5566 7 75.25 7C112.943 7 143.5 37.5566 143.5 75.25C143.5 112.943 112.943 143.5 75.25 143.5Z" stroke="#78AEFF" stroke-width="14" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>

            <p class="cardtext">Precision Chisel</p>
        </Cards>

        <Cards variant="inner">
            <svg class="card-svg" width="182" height="182" viewBox="0 0 182 182" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M144.083 83.4167C160.836 83.4167 174.417 96.9974 174.417 113.75C174.417 130.503 160.836 144.083 144.083 144.083L45.5002 144.084C24.5594 144.084 7.5835 127.106 7.5835 106.166C7.5835 86.0695 23.2208 69.626 42.9897 68.3321C51.4924 50.3537 69.7922 37.9167 91.0002 37.9167C117.744 37.9167 139.873 57.6943 143.55 83.4214C143.729 83.4183 143.904 83.4167 144.083 83.4167Z" stroke="#78AEFF" stroke-width="14" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>

            <p class="cardtext">Etched in Memory</p>
        </Cards>

        <Cards variant="inner">
            <svg class="card-svg" width="136" height="151" viewBox="0 0 136 151" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M75.25 52.5H7M75.25 52.5V19.1341C75.25 14.887 75.2471 12.7619 74.4206 11.1397C73.6935 9.71283 72.5423 8.55357 71.1154 7.82653C69.4932 7 67.3637 7 63.1167 7H7V52.5M75.25 52.5H116.2C120.447 52.5 122.577 52.5 124.199 53.3265C125.626 54.0536 126.777 55.2128 127.504 56.6397C128.33 58.2619 128.333 60.387 128.333 64.6341V85.8674C128.333 90.1145 128.33 92.235 127.504 93.8572C126.777 95.2841 125.626 96.4472 124.199 97.1743C122.578 98 120.454 98 116.215 98H98M7 52.5V98M7 98V143.5H85.8821C90.1209 143.5 92.2448 143.5 93.8653 142.674C95.2922 141.947 96.4435 140.785 97.1706 139.358C97.9971 137.736 98 135.614 98 131.367V98M7 98H98" stroke="#78AEFF" stroke-width="14" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>

            <p class="cardtext">Structured Clarity</p>
        </Cards>

        <Cards variant="inner">
            <svg class="card-svg" width="136" height="150" viewBox="0 0 136 150" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M90.4167 52.5L60.0833 82.8333L44.9167 67.6667M128.333 61.335C128.333 111.144 90.6588 133.475 74.6872 140.705L74.667 140.714C72.9873 141.474 72.1452 141.855 70.2364 142.183C69.0276 142.39 66.3134 142.39 65.1045 142.183C63.1881 141.854 62.3373 141.471 60.6441 140.705C44.6725 133.475 7 111.144 7 61.3349V31.2681C7 22.774 7 18.5238 8.65307 15.2795C10.1071 12.4257 12.4257 10.1071 15.2795 8.65307C18.5238 7 22.774 7 31.2681 7H104.068C112.562 7 116.803 7 120.048 8.65307C122.902 10.1071 125.228 12.4257 126.682 15.2795C128.333 18.5206 128.333 22.7657 128.333 31.2432V61.335Z" stroke="#78AEFF" stroke-width="14" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>

            <p class="cardtext">Inflexible Integrity</p>
        </Cards>
    </div>
</div>

<style>
*{
    margin: 0;
    padding: 0; 
}
    #section4 {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: var(--spacing-64);
        width: 100%;
        padding: 80px;
        background-color: var(--color-bg-primary);
        height: fit-content;
    }

    #textcontainer {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 10px;
    }

    #textcontainer p{
        font-family: var(--font-inter);
        font-weight: 200px;
        font-size: 32px;
        color: var(--color-text-secondary);
    }

    #cardcontainer {
        display: flex;
        gap: var(--spacing-32);
        flex-wrap: wrap;
        justify-content: center;
        padding: var(--spacing-40);
    }

    .cardtext {
        font-family: var(--font-inter);
        font-weight: var(--font-weight-semibold);
        font-size: 32px;
        color: var(--color-text-secondary);
    }

    @media (max-width: 768px){
        #textcontainer p{
        font-family: var(--font-inter);
        font-weight: 200px;
        font-size: 16px;
        color: var(--color-text-secondary);
        text-align: center;
    }

    #textcontainer h1{
        font-family: var(--font-inter);
        font-weight: var(--font-weight-bold);
        font-size: 56px;
        text-align: center;
    }
    
}

    @media (max-width: 600px){
        #section4 {
            padding: var(--spacing-40);
            width: 100vw;
        }   
            #textcontainer p{
                font-size: 16px;
            }
            #textcontainer h1{
                font-size: 40px;
                text-align: center;
            }
        
         .card-svg{
           width: 121px;
              height: 121px;
              stroke-width: 9px;
        }
    }
</style>
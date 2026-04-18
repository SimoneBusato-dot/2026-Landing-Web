<script>
    let { variant = 'primary', children} = $props();
</script>

{#if variant === 'primary'}
<button class={`btn btn-${variant}`}>
{@render children?.()}
    <svg xmlns="http://www.w3.org/2000/svg" height="40px" viewBox="0 -960 960 960" width="40px" fill="#e3e3e3"><path d="M127.33-240 80-287.33l293.33-293.34L538-416l230-229.33H648.67V-712H880v231.33h-66v-116.66L537.33-320.67 372.67-485.33 127.33-240Z"/></svg>
    
</button>
{:else}
<button class={`btn btn-${variant}`}>
    {@render children?.()}
</button>

{/if}

<style>
    .btn {
        display: flex;
        align-items: center;
        justify-content: center;
        height: 57px;
        border-radius: var(--radius-full);
        font-family: var(--font-inter);
        font-weight: var(--font-weight-semibold);
        font-size: 24px;
        cursor: pointer;
        border: none;
        transition: all 0.2s ease;
    }
    
    .btn-primary {
        background-color: var(--color-btn-primary-bg);
        color: var(--color-btn-primary-text);
        padding: var(--radius-s) var(--spacing-32);
        box-shadow: -3px -4px 4px 0px var(--color-neomorph-light),
        3px 2px 4px 0px var(--color-neomorph-shadow);
        position: relative;
        transition: all 0.2s ease;
         
    }
    
    .btn-primary svg{
        opacity: 0;
        position: absolute;
        right: 16px;
        transition: all 0.2s ease;

    }

    .btn-primary:hover svg{
        opacity: 1;
        position: relative;
        right: 0;
    }

    
    .btn-secondary {
        background-color: var(--color-bg-primary);
        color: var(--color-btn-secondary-text);
        padding: var(--radius-s) var(--spacing-32);
        box-shadow: inset -3px -4px 4px 0px var(--color-neomorph-light),
        inset 3px 2px 4px 0px var(--color-neomorph-shadow);
        transition: all 0.2s ease;
    }
    
    .btn-secondary:hover {
        background-color: var(--color-btn-hover-bg);
        box-shadow: inset -3px -4px 4px 0px var(--color-btn-hover-bg),
        inset 3px 2px 4px 0px var(--color-btn-hover-bg);
    }

    @media (max-width: 646px){
        .btn {
            font-size: 20px;
        }

        .btn-primary, .btn-secondary {
            padding: var(--radius-s) var(--spacing-16);
        }

        .btn-primary svg {
            display: none;
        }
    }
</style>
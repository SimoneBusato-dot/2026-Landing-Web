<script>
    let { variant = 'primary', children} = $props();
</script>

{#if variant === 'primary'}
<button class={`btn btn-${variant}`}>
{@render children?.()}
<svg width="27" height="18" viewBox="0 0 27 18" fill="none" xmlns="http://www.w3.org/2000/svg">
<path d="M25.5007 1.5L16.7314 10.4062C16.574 10.5662 16.4943 10.6464 16.4238 10.7095C15.2848 11.729 13.5624 11.729 12.4233 10.7095C12.3528 10.6464 12.2726 10.5663 12.115 10.4062C11.9574 10.2462 11.8786 10.1661 11.8081 10.103C10.6691 9.08352 8.94595 9.08352 7.80691 10.103C7.73656 10.166 7.65798 10.2458 7.50117 10.4051L1.5 16.5M25.5007 1.5L25.5 10.5M25.5007 1.5H16.5" stroke="#EEEEEE" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
</svg>
    
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
        gap: 8px;
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
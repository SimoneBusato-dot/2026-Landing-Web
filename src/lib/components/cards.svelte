<script>
let{variant = 'drop', children} = $props();
</script>

<div class={`card card-${variant}`}>
	{@render children?.()}
</div>

<style>
    .card {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        border-radius: var(--radius-md);
        padding: var(--spacing-32);
        gap: 10px;
        width: 600px;
        height: 311px;
        background-color: var(--color-bg-secondary);
    }

    .card-drop {
        box-shadow: -3px 2px 4px 0px var(--color-neomorph-shadow);
    }

    .card-inner{
        box-shadow: inset -3px -4px 4px 0px var(--color-neomorph-light),
        inset 3px 2px 4px 0px var(--color-neomorph-shadow);
    }

    @media (max-width: 600px){
        .card{
            width: 340px;
            height: fit-content;
        }
    }
</style>
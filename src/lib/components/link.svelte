<script>
    let { variant = 'default', children} = $props();
</script>

<button class={`link link-${variant}`}>
    {@render children?.()}

</button>


<style>
    .link-default {
        color: var(--color-text-primary);
        text-decoration: none;
        font-family: var(--font-inter);
        font-weight: var(--font-weight-semibold);
        font-size: 24px;
        transition: all 0.2s ease;
        padding: var(--spacing-8) var(--spacing-16);
        background-color: var(--color-bg-primary);
        box-shadow: inset -3px -4px 4px 0px var(--color-bg-primary),
        inset 3px 2px 4px 0px var(--color-bg-primary);
        border: none;
        border-radius: var(--radius-full);
        width: fit-content;
        height: fit-content;
    }

    .link-default:hover {
        box-shadow: inset -3px -4px 4px 0px var(--color-neomorph-light),
        inset 3px 2px 4px 0px var(--color-neomorph-shadow);
    }

    .link-active {
        color: var(--color-link-hover);
        text-decoration: none;
        font-family: var(--font-inter);
        font-weight: var(--font-weight-semibold);
        font-size: 24px;
        transition: all 0.2s ease;
        padding: var(--spacing-8) var(--spacing-16);
        background-color: var(--color-bg-primary);
        box-shadow: inset -3px -4px 4px 0px var(--color-neomorph-light),
        inset 3px 2px 4px 0px var(--color-neomorph-shadow);
        border: none;
        border-radius: var(--radius-full);
        width: fit-content;
        height: fit-content;
    }
</style>
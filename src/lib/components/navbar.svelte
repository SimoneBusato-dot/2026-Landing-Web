<script>
    import Link from "./link.svelte";
</script>
<div id="nav-container">
    <nav>
        <p id="Logo">ED</p>
        <div id="link-container">
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
        top: 7%;
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
        overflow: hidden;
        
        
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
</style>
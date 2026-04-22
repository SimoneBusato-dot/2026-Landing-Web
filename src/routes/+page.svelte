<script>
    import NavBar from "$lib/components/navbar.svelte";
    import Herosection from "$lib/components/herosection.svelte";
    import Section4 from "$lib/components/section4.svelte";
    import Section2 from "$lib/components/section2.svelte";
</script>

<NavBar />
<Herosection />
<Section2 />
<Section4 />


<style>
   :global(html, body) {
    margin: 0;
    padding: 0;
    width: 100%;
    overflow-x: clip; 
}
</style>

  
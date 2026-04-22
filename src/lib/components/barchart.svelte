<script>
    import * as d3 from 'd3';
    import {onMount} from 'svelte';
    let data = [10, 5, 8.5, 10, 2.5, 5.5, 10];
    let svgElement;

    onMount(async () => {
        const svg = d3.select(svgElement);
        const box = svgElement.getBoundingClientRect();
        const width = box.width;
        const height = box.height;
        const margin = {top: 10, right: 10, bottom: 10, left: 10};
        const innerWidth = width - margin.right - margin.left;
        const innerHeight = height - margin.top - margin.bottom;

        const render = data =>{
            const xScale = d3.scaleBand()
                .domain(data.map((d, i) => i))
                .range([0, innerWidth])
                .padding(0.4)

            const yScale = d3.scaleLinear()
                .domain([0, d3.max(data)])
                .range([innerHeight, innerHeight*0.02])

            const g = svg.append('g')

            g.selectAll('rect').data(data)
                .enter().append('rect')
                .attr('x', (d, i) => xScale(i))
                .attr('y', d => yScale(d))
                .attr('width', xScale.bandwidth())
                .attr('height', d => innerHeight - yScale(d))
                .attr('fill', 'steelblue')
                .attr('rx', 25)
        }

        render(data);
    })
</script>

<svg bind:this={svgElement} width="600" height="311">
    <defs>
        <linearGradient id="Bar-Gradient" x1="270" y1="20" x2="270" y2="236" gradientUnits="userSpaceOnUse">
        <stop stop-color="#78AEFF"/>
        <stop offset="1" stop-color="#376CDB" />
        </linearGradient>
    </defs>
</svg>

<style>
    :global(rect){
        fill: url(#Bar-Gradient);
        filter: drop-shadow(-3px -4px 2px var(--color-neomorph-light)) drop-shadow(3px 2px 2px var(--color-neomorph-shadow));

    }
</style>
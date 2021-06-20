<script>
import { fade, draw, fly } from 'svelte/transition';

	export let height             = '50px';
	export let width              = '50px';
	export let viewBox            = "0 0 64 64";
	export let title              = "title";
	export let stroke             = "#202020";
	export let hover_stroke       = "#202020";
	export let inner_stroke       = "#202020";
	export let hover_inner_stroke = "#202020";
	export let fill               = "none";
	export let hover_fill         = "none";

  let temp_fill         = fill;
  let temp_stroke       = stroke;
  let temp_inner_stroke = inner_stroke;

  function handleMouseOver(e) {
		fill = hover_fill;
		stroke = hover_stroke;
		inner_stroke = hover_inner_stroke;
	}
	function handleMouseOut(e) {
		fill = temp_fill;
		stroke = temp_stroke;
		inner_stroke = temp_inner_stroke;
	}

 
	
    
</script>
<style>
svg {
  transition: all 275ms ease;
}
</style>


<svg out:fade="{{duration: 200}}" on:mouseover={handleMouseOver} on:mouseout={handleMouseOut}  width={width} height={height} viewBox={viewBox} aria-labelledby={title}
aria-describedby="desc" role="img" xmlns:xlink="http://www.w3.org/1999/xlink">
  <title>{title}</title>
  
  <circle data-name="layer2"
  cx="32" cy="32" r="30" fill={fill} stroke={stroke} stroke-miterlimit="10"
  stroke-width="2" stroke-linejoin="round" stroke-linecap="round"></circle>
  <path data-name="layer1" fill="none" stroke={inner_stroke} stroke-miterlimit="10"
  stroke-width="2" d="M32 16v32m16-16H16" stroke-linejoin="round" stroke-linecap="round"></path>
</svg>
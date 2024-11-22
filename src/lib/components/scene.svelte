<script lang="ts">
	import { T } from '@threlte/core';
	import { Align } from '@threlte/extras';
	import Trees from './trees.svelte';
	import { Color } from 'three';
</script>

<T.AmbientLight intensity={0.1} />
<T.DirectionalLight
	color="white"
	position={[15, 15, 15]}
	castShadow
	shadow.mapSize.width={2048}
	shadow.mapSize.height={2048}
/>

<Align auto>
	<Trees
		colors={[
			new Color('#427062').convertLinearToSRGB(),
			new Color('#33594e').convertLinearToSRGB(),
			new Color('#234549').convertLinearToSRGB(),
			new Color('#1e363f').convertLinearToSRGB()
		]}
	/>
</Align>

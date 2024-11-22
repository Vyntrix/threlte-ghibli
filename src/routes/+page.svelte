<script lang="ts">
	import Ground from '$lib/components/ground.svelte';
	import Scene from '$lib/components/scene.svelte';
	import { Canvas, T } from '@threlte/core';
	import { OrbitControls } from '@threlte/extras';
</script>

<div class="size-full h-screen">
	<Canvas>
		<Scene />
		<Ground />
		<T.PerspectiveCamera makeDefault position={[5, 5, 5]}>
			<OrbitControls enableDamping />
		</T.PerspectiveCamera>
	</Canvas>
</div>

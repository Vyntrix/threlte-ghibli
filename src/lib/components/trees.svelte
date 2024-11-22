<script lang="ts">
	import { T } from '@threlte/core';
	import { useGltf } from '@threlte/extras';
	import { Color, Vector3 } from 'three';
	import { GhibliShader } from '../shaders/ghibli-shader';

	let { colors, ...props } = $props();

	const gltf = useGltf('/trees.glb');

	const uniforms = () => {
		return {
			colorMap: {
				value: colors
			},
			brightnessThresholds: {
				value: [0.9, 0.45, 0.001]
			},
			lightPosition: {
				value: new Vector3(15, 15, 15)
			}
		};
	};
</script>

{#if $gltf}
	<T.Group {...props}>
		<T.Mesh
			castShadow
			receiveShadow
			geometry={$gltf.nodes.Foliage.geometry}
			position={[0.33, -0.05, -0.68]}
		>
			<T.ShaderMaterial attach="material" {...GhibliShader} uniforms={uniforms()} />
		</T.Mesh>
	</T.Group>
{/if}

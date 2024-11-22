<script lang="ts">
	import { T } from '@threlte/core';
</script>

<T.Mesh castShadow receiveShadow position={[0, -3.05, 0]} rotation={[-Math.PI / 2, 0, 0]}>
	<T.PlaneGeometry args={[100, 100, 1, 1]} />
	<T.ShadowMaterial opacity={0.4} />
</T.Mesh>

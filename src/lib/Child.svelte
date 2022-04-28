<script>
	import { onMount } from 'svelte';

	let anExternalProp = 1;

	onMount(() => {
		window.incrementExternalProp = () => (anExternalProp += 1);
		window.parent.setUpFrame();
	});
</script>

<p>
	{anExternalProp}
</p>

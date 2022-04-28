<script lang="ts">
	import { browser } from '$app/env';
	import Child from './Child.svelte';

	if (browser) {
		window.setUpFrame = () => {
			var frame = document?.getElementById('my-frame') as HTMLIFrameElement | null;
			var cWind = frame?.contentWindow;
			setInterval(() => cWind?.incrementExternalProp(), 1000);
		};
	}
</script>

<iframe id="my-frame" title="test" src="/iframe-source" />

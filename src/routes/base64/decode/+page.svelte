<script lang="ts">
	import Button from '$lib/components/ui/button/button.svelte';
	import * as Resizable from '$lib/components/ui/resizable';
	let x: string = '';
	$: decodedData = atob(x);
	import { ClipboardIcon } from '$lib/icons/clipboard';
	const copyToClipboard = () => {
		navigator.clipboard
			.writeText(decodedData)
			.then(() => {
				console.log('Text successfully copied to clipboard');
			})
			.catch((err) => {
				console.error('Unable to copy text to clipboard', err);
			});
	};
</script>

<svelte:head>
	<title>Decode Base64</title>
	<meta name="description" content="About this app" />
</svelte:head>

<div class="p-2 pt-0 h-full">
	<div class="flex justify-between rounded-md mb-2">
		<h2 class="flex items-center justify-center p-2">Encode Base64</h2>
		<Button variant="outline" on:click={copyToClipboard}>
			Copy to Clipboard
			<ClipboardIcon styles="ml-2 h-4 w-4" />
		</Button>
	</div>
	<Resizable.PaneGroup direction="horizontal" class="rounded-md border h-full">
		<Resizable.Pane
			><textarea
				bind:value={x}
				class="w-full h-full outline-none bg-inherit p-2 overflow-scroll"
			/></Resizable.Pane
		>
		<Resizable.Handle />
		<Resizable.Pane
			><textarea
				bind:value={decodedData}
				class="w-full h-full outline-none bg-inherit p-2 overflow-scroll"
			/></Resizable.Pane
		>
	</Resizable.PaneGroup>
</div>

<script lang="ts">
	import Themebutton from '$lib/components/themebutton/themebutton.svelte';
	import Button from '$lib/components/ui/button/button.svelte';
	import * as DropdownMenu from '$lib/components/ui/dropdown-menu';
</script>

<nav class="flex items-center justify-between p-2">
	<div>
		<a href="/"><Button variant="outline"><h1>Data Flow</h1></Button></a>
		<DropdownMenu.Root>
			<DropdownMenu.Trigger><Button variant="outline">Base 64</Button></DropdownMenu.Trigger>
			<DropdownMenu.Content>
				<a href="/base64/encode"
					><DropdownMenu.Item class="hover:cursor-pointer">Encode</DropdownMenu.Item></a
				>
				<a href="/base64/decode"
					><DropdownMenu.Item class="hover:cursor-pointer">Decode</DropdownMenu.Item></a
				>
			</DropdownMenu.Content>
		</DropdownMenu.Root>
		<DropdownMenu.Root>
			<DropdownMenu.Trigger><Button variant="outline">JSON</Button></DropdownMenu.Trigger>
			<DropdownMenu.Content>
				<a href="/"><DropdownMenu.Item class="hover:cursor-pointer">Beautify</DropdownMenu.Item></a>
				<a href="/"><DropdownMenu.Item class="hover:cursor-pointer">Decode</DropdownMenu.Item></a>
			</DropdownMenu.Content>
		</DropdownMenu.Root>
	</div>
	<Themebutton />
</nav>

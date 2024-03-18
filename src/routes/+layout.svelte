<script lang="ts">
	import Navbar from '../lib/components/navbar/navbar.svelte';
	import '../app.pcss';
	import { ModeWatcher } from 'mode-watcher';
</script>

<ModeWatcher />
<Navbar />
<slot />

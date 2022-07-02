<script lang="ts">
	import { browser } from '$app/env';

	type Todo = {
		uid: string;
		created_at: Date;
		text: string;
		done: boolean;
		pending_delete: boolean;
	};

	export let todos: Todo[];

	console.log('todos?', todos);
	const performance = () => {
		if (browser) {
			const currentTime = new Date();
			// round trip time
			const fullTime = currentTime - window.performance.timing.requestStart;
			return fullTime;
		}
	};
</script>

<svelte:head>
	<title>Todos</title>
	<meta name="description" content="A todo list app" />
</svelte:head>

<div>
	<div>
		<h2>
			Request-to-paint time: {performance()}
			ms
		</h2>
		<a href="/">Back</a>
	</div>
</div>

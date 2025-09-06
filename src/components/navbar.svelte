<script lang="ts">
	import type { Category } from '$lib/model/category';

	interface Props {
		categories: Category[];
		states: {
			current_category: number;
		};
	}

	let { categories, states }: Props = $props();
	let order_count = $state(0);
	const add_order = () => {
		order_count += 1;
	};
</script>

<nav
	class="fixed inset-1 top-12 left-5 h-2/4 w-[22%] overflow-y-scroll rounded-lg bg-white p-4 ring-1 ring-black/20"
>
	<h1 class="letter-spacing pb-2 text-3xl font-semibold">Category</h1>
	<ul
		class="mt-2 ml-1 text-lg font-semibold *:rounded-lg *:px-1 *:py-2 *:tracking-[8%] *:duration-75 *:hover:bg-black/5"
	>
		<li class="category-active">Coffee</li>
		<li>Matcha</li>
		<li>Pastry</li>
		<li>Artisan Bread</li>
	</ul>
</nav>

<script lang="ts">
	import Navbar from '../components/navbar.svelte';
	import type { Category } from '$lib/model/category';
	import type { Product } from '$lib/model/product';
	import ItemCard from '../components/item_card.svelte';

	let current_category = $state(0);

	const products: Product[] = [
		{
			name: 'Latte',
			price: 25_000
		},
		{
			name: 'Cappucino',
			price: 25_000
		},
		{
			name: 'Espresso',
			price: 25_000
		},
		{
			name: 'Machiato',
			price: 25_000
		}
	];

	let idx = 0;
	const categories: Category[] = [
		{
			id: idx++,
			name: 'Coffee'
		},
		{
			id: idx++,
			name: 'Matcha'
		},
		{
			id: idx++,
			name: 'Milk base'
		},
		{
			id: idx++,
			name: 'Dessert'
		}
	];

	const format_idr = (amount: number): String => {
		return 'Rp' + amount.toLocaleString('id-ID');
	};

	$inspect(current_category);
</script>

<Navbar {categories} states={{ current_category }} />
<main
	class="mt-12 ml-[25%] h-max pr-8
"
>
	<h1 class="border-b-2 pb-2 pl-2 text-4xl font-semibold tracking-[8%]">Coffee</h1>
	<section class="mt-2 grid grid-cols-1 gap-4 p-4 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4">
		<ItemCard name="Cappucino" price="25.000" />
		<ItemCard name="Espresso Matcha" price="25.000" />
		<ItemCard name="Latte" price="25.000" />
		<ItemCard name="Machiato" price="25.000" />
		<ItemCard name="Kopi Susu" price="25.000" />
		<ItemCard name="Cold Brew" price="25.000" />
		<ItemCard name="Kopi yang bikin adem" price="25.000" />
	</section>
</main>
<div class="fixed"></div>

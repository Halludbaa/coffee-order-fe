<script>
	let order_count = $state(0);
	const add_order = () => {
		order_count += 1;
	};
</script>

<nav class="fixed top-0 flex h-screen w-1/4 flex-col items-stretch bg-white p-4 shadow">
	<h1 class="text-4xl font-bold">MoreCoffee</h1>
	<section class="drop-shadow-x mt-8 flex flex-col rounded-2xl p-2">
		<h3 class="mb-2 text-xl font-semibold">Category</h3>
		<ul
			class="flex flex-col gap-1 *:rounded-lg *:p-2 *:hover:-translate-x-1 *:hover:bg-gray-100 *:hover:font-bold *:hover:duration-150"
		>
			<li class="-translate-x-1 bg-gray-100 font-bold">
				<a href="https://youtube.com" aria-label="true">Coffee</a>
			</li>
			<li class=" "><a href="https://youtube.com" aria-label="true">Matcha </a></li>
			<li class=" "><a href="https://youtube.com" aria-label="true">Milk Base</a></li>
			<li class=" "><a href="https://youtube.com" aria-label="true">Dessert</a></li>
		</ul>
	</section>
	<button class="mt-auto rounded-xl bg-black py-2 text-2xl font-bold text-white" onclick={add_order}
		>Order ({order_count})</button
	>
</nav>

<script lang="ts">
	interface Props {
		name: String;
		price: String;
	}

	let { name, price }: Props = $props();
</script>

<div class="flex flex-col">
	<div class="h-[250px] w-full rounded-lg bg-[#A69595]"></div>
	<span class="px-1 text-lg font-semibold">{name}</span>
	<span class="px-1 text-lg font-semibold tracking-[8%]">Rp. {price}</span>
</div>

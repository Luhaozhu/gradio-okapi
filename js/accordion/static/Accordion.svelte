<script lang="ts">
	export let label = "";
	export let open = true;
</script>

<!-- TODO: fix -->
<!-- svelte-ignore a11y-click-events-have-key-events -->
<!-- svelte-ignore a11y-no-static-element-interactions -->
<div on:click={() => (open = !open)} class="label-wrap" class:open>
	<span>{label}</span>
	<span style:transform={open ? "rotate(0)" : "rotate(90deg)"} class="icon">
		▼
	</span>
</div>
<div style:display={open ? "block" : "none"}>
	<slot />
</div>

<style>
	span {
		font-weight: var(--section-header-text-weight);
		font-size: var(--section-header-text-size);
	}
	.label-wrap {
		display: flex;
		justify-content: space-between;
		cursor: pointer;
		width: var(--size-full);
	}
	.label-wrap.open {
		margin-bottom: var(--size-2);
	}

	.icon {
		transition: 150ms;
	}
</style>

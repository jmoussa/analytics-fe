<script>
    import { goto } from '$app/navigation';
    import Button from '$lib/Button.svelte'
</script>

<svelte:head>
  <title>About</title>
</svelte:head>

<main>
	<div class="hero py-60">
		<div class="text-center hero-content">
			<div>
				<div class="p-5">
					<h1 class="p-2 text-5xl font-bold">COVID-19 HQ</h1>
				</div>
				<div class="p-5">
					<Button 
                        class="btn btn-primary"
                        label="Go to dashboard"
                        on:click={() => {
                            goto(`./dashboard`, {
                                noscroll: true,
                                keepfocus: true
                            });
                        }}
                    >Get In Ladz</Button>
				</div>
			</div>
		</div>
	</div>
</main>

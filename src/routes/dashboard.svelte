<script>
    import LineChart from '$lib/LineChart.svelte';
    import apiData from '../stores/store.js';
    export let labels = {};
    export let colors = {};
    export let options = {};
    export let query = {
        "query": "covid-data",
    };

    // fetch data
    onMount(async () => {
        fetch("localhost:8000/api", {
                method: 'POST', // *GET, POST, PUT, DELETE, etc.
                mode: 'cors', // no-cors, *cors, same-origin
                cache: 'no-cache', // *default, no-cache, reload, force-cache, only-if-cached
                credentials: 'same-origin', // include, *same-origin, omit
                headers: {
                'Content-Type': 'application/json',
                'API-KEY': '0000',
                // 'Content-Type': 'application/x-www-form-urlencoded',
                },
                redirect: 'follow', // manual, *follow, error
                referrerPolicy: 'no-referrer', // no-referrer, *no-referrer-when-downgrade, origin, origin-when-cross-origin, same-origin, strict-origin, strict-origin-when-cross-origin, unsafe-url
                body: JSON.stringify(query) // body data type must match "Content-Type" header
            })
            .then(res => res.json())
            .then(data => {
                apiData.set(data);
            })
            .catch(error => {
                console.error(error);
                return [];
            });
    });
</script>

<svelte:head>
  <title>Dashboard</title>
</svelte:head>

<main>
	<div class="hero py-60">
		<div class="text-center hero-content">
			<div>
				<div class="p-5">
					<h1 class="p-2 text-5xl font-bold">COVID-19 Dashboard</h1>
				</div>
                <div>
                    <LineChart
                        :data={apiData}
                        :labels={labels}
                        :options={options}
                        :colors={colors}>
                    </LineChart>
                </div>
			</div>
		</div>
	</div>
</main>

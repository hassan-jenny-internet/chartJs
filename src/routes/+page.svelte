<script>
	import { browser } from '$app/environment';
	let xValues = ['Italy', 'France', 'Spain', 'USA', 'Argentina'];
	let yValues = [55, 49, 44, 24, 15];
	let barColors = ['#b91d47', '#00aba9', '#2b5797', '#e8c3b9', '#1e7145'];

	const renderGrid = () => {
		new Chart('myChart', {
			type: 'pie',
			data: {
				labels: xValues,
				datasets: [
					{
						backgroundColor: barColors,
						data: yValues
					}
				]
			},
			options: {
				title: {
					display: true,
					text: 'World Wide Wine Production 2018'
				}
			}
		});
	};
</script>

<svelte:head>
	{#if browser}
		<script
			on:load={renderGrid}
			src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.9.4/Chart.js"
		></script>
	{/if}
</svelte:head>

<canvas id="myChart" style="width:100%;max-width:600px" />

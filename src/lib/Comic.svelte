<script lang="ts">
	import { formatDistance } from 'date-fns';
	import { onMount } from 'svelte';
	interface Joke {
		safe_title: string;
		img: string;
		alt: string;
		year: number;
		month: number;
		day: number;
	}
	let title: HTMLElement;
	let img: HTMLImageElement;
	let date: HTMLElement;
	onMount(() => {
		async function main(): Promise<void> {
			async function fetchId(): Promise<string> {
				const params: URLSearchParams = new URLSearchParams();
				params.append('email', 'a.sarhan@innopolis.university');
				const response: Response = await fetch(
					'https://fwd.innopolis.university/api/hw2?' + params.toString()
				);
				const data: string = await response.json();
				return data;
			}

			async function fetchJoke(): Promise<Joke> {
				const jokeId: string = await fetchId();
				const params: URLSearchParams = new URLSearchParams();
				params.append('id', jokeId);
				const response: Response = await fetch(
					'https://fwd.innopolis.university/api/comic?' + params.toString()
				);
				const joke: Joke = await response.json();
				return joke;
			}

			const joke: Joke = await fetchJoke();

			title.textContent = joke.safe_title;
			img.src = joke.img;
			img.alt = joke.alt;

			const event: Date = new Date(Date.UTC(joke.year, joke.month, joke.day));

			const timePassed: string = formatDistance(new Date(), event, { addSuffix: true });
			date.textContent = timePassed;
		}

		main();
	});
</script>

<section id="my-joke" class="joke">
	<h2 bind:this={title} id="joke-title">Joke title</h2>
	<p bind:this={date} id="upload-date" />
	<!-- svelte-ignore a11y-img-redundant-alt -->
	<img bind:this={img} id="joke-image" src="." alt="joke-image" />
</section>

<style>
	.joke {
		padding: 0 10%;
		height: 80vh;
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.joke p {
		font-size: 30px;
		margin-top: 10px;
		margin-bottom: 20px;
		color: rgba(43, 238, 232, 0.978);
	}

	.joke img {
		min-width: 40vh;
		min-height: 40vh;
		max-width: 100vh;
		font-size: 20px;

		text-align: center;
	}
</style>

<script>
	import Counter from './Counter.svelte';
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcome_fallback from '$lib/images/svelte-welcome.png';
	import profile from '$lib/images/black-santy.png';
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<img src={profile} alt="santy profile" width="250" height="250" />
	<h1>
		Santhosh Prabakar Badhri<br />
		<span style="font-size:21px; font-style: italic">Design & Develop</span>
	</h1>
	<p>
		Experienced UI/UX Architect with 12+ years in designing and optimizing digital products across
		Banking, Ecommerce, Real Estate, and Healthcare. Skilled in ReactJS, Tailwind CSS, and UX
		research, with a strong focus on design systems and accessibility. Seeking a challenging role as
		a UI/UX Architect or Product Manager to drive innovative, user-centered solutions. Open to
		opportunities in Hyderabad or Remote.
	</p>
	<button class="download-btn" on:click={() => window.open('/santhosh_Apr.docx', '_blank')}>
		📄 Download Resume
	</button>
</section>

<style>
	img {
		border-radius: 250px;
	}
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}

	h1 {
		width: 100%;
	}

	p {
		text-align: center;
	}

	.download-btn {
		background-color: #007acc;
		color: #fff;
		padding: 10px 20px;
		font-weight: bold;
		border: none;
		border-radius: 6px;
		cursor: pointer;
		text-decoration: none;
		display: inline-block;
		margin-top: 1rem;
	}

	.download-btn:hover {
		background-color: #005fa3;
	}
</style>

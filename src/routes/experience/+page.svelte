<script lang="ts">
	type Experience = {
		company: string;
		title: string;
		duration: string;
		responsibilities: string[];
	};

	let experiences: Experience[] = [
		{
			company: 'HSBC (Purview Services)',
			title: 'UI/UX Lead',
			duration: 'Aug 2023 – Present',
			responsibilities: [
				'Providing visionary leadership',
                'Architecting and implementing innovative UI/UX solutions.',
                'Championing usability testing and user research.'

			]
		},
		{
			company: 'Systemsoft',
			title: 'UI Lead',
			duration: 'Apr 2023 – Aug 2023',
			responsibilities: [
				'Optimized scalable architecture with reusable components.',
				'Improved delivery speed by 40%.'
			]
		},
		{
			company: 'Callaway Golf',
			title: 'UI Lead',
			duration: 'Oct 2022 – Jan 2023',
			responsibilities: ['Enhanced SAP eCommerce UI and microsites.', 'Improved engagement by 25%.']
		},
		{
			company: 'Infosys (Nithyo Infotech)',
			title: 'Senior Developer',
			duration: 'Jul 2022 – Oct 2022',
			responsibilities: [
				'Modernized enterprise UIs using React.',
				'Boosted frontend performance and accessibility.'
			]
		},
		{
			company: '10X Incubator',
			title: 'UI Lead',
			duration: 'Dec 2021 – Mar 2022',
			responsibilities: [
				'Delivered VueJS apps and UX research-based design.',
				'Mentored developers under tight schedules.'
			]
		},
		{
			company: 'Indegene',
			title: 'Web Lead',
			duration: 'May 2021 – Nov 2021',
			responsibilities: ['Built SEO-optimized web apps.', 'Increased search visibility by 20%.']
		},
		{
			company: 'Skuad',
			title: 'Senior Developer',
			duration: 'Oct 2015 – Jan 2021',
			responsibilities: ['Developed SAP/Hybris UIs and mentored devs.']
		},
		{
			company: 'Sitosys E-Media Pvt. Ltd.',
			title: 'Junior Designer',
			duration: 'Jul 2012 – Oct 2015',
			responsibilities: ['Designed responsive websites and ran SEO campaigns.']
		}
	];
</script>

<h2 class="section-title">Experience:</h2>

<div class="card-grid">
	{#each experiences as exp}
		<div class="card">
			<div class="header">
				<h3>{exp.title}</h3>
				<span class="duration">{exp.duration}</span>
			</div>
			<p class="company">{exp.company}</p>
			<ul>
				{#each exp.responsibilities as item}
					<li>{item}</li>
				{/each}
			</ul>
		</div>
	{/each}
</div>

<style>
	.section-title {
		text-align: center;
		margin: 2rem 0 1.5rem;
		font-size: 1.8rem;
	}

	.card-grid {
		display: grid;
		grid-template-columns: repeat(3, 1fr); /* Always 3 per row on wide screens */
		gap: 1.5rem;
		padding: 1rem;
		max-width: 1200px;
		margin: 0 auto;
		justify-items: center;
	}

	.card {
		background-color: #f8f9fa;
		border: 1px solid #ddd;
		border-radius: 10px;
		padding: 1.2rem;
		box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
		transition: transform 0.2s ease;
	}

	.card:hover {
		transform: translateY(-5px);
	}

	.header {
		display: flex;
		justify-content: space-between;
		align-items: baseline;
		margin-bottom: 0.5rem;
	}

	.company {
		font-weight: bold;
		color: #007acc;
		margin-bottom: 0.5rem;
	}

	.duration {
		font-size: 0.9rem;
		color: #777;
	}

	ul {
		margin-top: 0.5rem;
		padding-left: 1rem;
		font-size: 0.95rem;
	}

	ul li {
		margin-bottom: 0.4rem;
		line-height: 1.3;
	}

	@media (max-width: 500px) {
		.card {
			padding: 1rem;
		}

		.header h3 {
			font-size: 1rem;
		}

		.company {
			font-size: 0.95rem;
		}
	}
	@media (max-width: 992px) {
		.card-grid {
			grid-template-columns: repeat(2, 1fr); /* 2 in a row on medium screens */
		}
	}

	@media (max-width: 600px) {
		.card-grid {
			grid-template-columns: 1fr; /* 1 in a row on small screens */
		}
	}
</style>

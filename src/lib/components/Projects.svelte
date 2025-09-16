<script>
	import { ExternalLink, Github } from 'lucide-svelte';

	import weatherProject from '$lib/assets/weather.png';
	import todoList from '$lib/assets/todo.png';
	import tmdb from '$lib/assets/tmdb.png';

	const projects = [
		{
			title: 'Mini Weather App',
			description: 'A convenient weather app built with Sveltekit, Tailwind, and OpenWeather api.',
			image:  weatherProject,
			tech: ['Svelte', 'Javascript', 'Tailwind CSS', 'OpenWeather'],
			github: '#',
			demo: 'https://weatherapp-be1.netlify.app'
		},
		{
			title: 'To Do List App',
			description: 'Your typical To DO list but more fancy.',
			image: todoList,
			tech: ['Svelte', 'Javascript', 'Tailwind CSS'],
			github: '#',
			demo: 'https://todolist1333.netlify.app'
		},
		{
			title: 'Svelte TMDB',
			description: 'A small showcase of the TMDB api with sveltekit.',
			image: tmdb,
			tech: ['Svelte', 'Javascript', 'Tailwind CSS', 'TMDB'],
			github: '#',
			demo: 'https://svelte-tmdb-be.netlify.app'
		},
		
	];
</script>

<section id="projects" class="py-20 bg-gradient-to-br from-slate-900 via-purple-900 to-blue-950">
	<div class="container mx-auto px-6">
		<div class="max-w-6xl mx-auto">
			<h2 class="text-4xl md:text-5xl font-bold text-center text-white mb-16">
				Featured <span class="text-transparent bg-clip-text bg-gradient-to-br from-purple-400 to-pink-400">Projects</span>
			</h2>

			<div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
				{#each projects as project}
					<div class="bg-slate-800/50 rounded-xl overflow-hidden border border-slate-700 hover:border-purple-500 transition-all duration-300 transform hover:scale-105">
						<div class="relative overflow-hidden">
							<img 
								src={project.image} 
								alt={project.title}
								class="w-full h-48 object-cover transition-transform duration-300 hover:scale-110"
							/>
							<div class="absolute inset-0 bg-gradient-to-t from-slate-900/50 to-transparent"></div>
						</div>

						<div class="p-6">
							<h3 class="text-xl font-bold text-white mb-2">{project.title}</h3>
							<p class="text-gray-300 mb-4 text-sm leading-relaxed">{project.description}</p>
							
							<div class="flex flex-wrap gap-2 mb-4">
								{#each project.tech as tech}
									<span class="bg-purple-600/20 text-purple-300 px-2 py-1 rounded text-xs">
										{tech}
									</span>
								{/each}
							</div>

							<div class="flex space-x-4">
								<a 
									href={project.github} 
									class="flex items-center text-gray-400 hover:text-white transition-colors"
								>
									<Github size={18} />
									<span class="ml-2 text-sm">Code</span>
								</a>
								<a 
									href={project.demo} 
									class="flex items-center text-gray-400 hover:text-white transition-colors"
								>
									<ExternalLink size={18} />
									<span class="ml-2 text-sm">Demo</span>
								</a>
							</div>
						</div>
					</div>
				{/each}
			</div>
		</div>
	</div>
</section>
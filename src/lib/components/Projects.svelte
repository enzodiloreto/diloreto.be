<script>
	import { ExternalLink, Github } from 'lucide-svelte';

	const projects = [
		{
			title: 'E-Commerce Platform',
			description: 'A full-stack e-commerce solution built with SvelteKit and Stripe integration.',
			image: 'https://images.unsplash.com/photo-1556742049-0cfed4f6a45d?w=600&h=300&fit=crop',
			tech: ['SvelteKit', 'TypeScript', 'Tailwind CSS', 'Stripe'],
			github: 'https://github.com',
			demo: 'https://example.com'
		},
		{
			title: 'Task Management App',
			description: 'A collaborative project management tool with real-time updates and team features.',
			image: 'https://images.unsplash.com/photo-1611224923853-80b023f02d71?w=600&h=300&fit=crop',
			tech: ['React', 'Node.js', 'Socket.io', 'MongoDB'],
			github: 'https://github.com',
			demo: 'https://example.com'
		},
		{
			title: 'Portfolio Website',
			description: 'A responsive portfolio built with modern web technologies and smooth animations.',
			image: 'https://images.unsplash.com/photo-1460925895917-afdab827c52f?w=600&h=300&fit=crop',
			tech: ['SvelteKit', 'Three.js', 'GSAP', 'Tailwind CSS'],
			github: 'https://github.com',
			demo: 'https://example.com'
		}
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
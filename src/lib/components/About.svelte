<script>
	import { Code, Palette, Database, Globe } from 'lucide-svelte';

	const skills = [
		{ name: 'Frontend', icon: Code, items: ['Svelte', 'React', 'TypeScript'] },
		{ name: 'Design', icon: Palette, items: ['UI/UX', 'Figma', 'Tailwind CSS', 'Animation'] },
		{ name: 'Backend', icon: Database, items: ['Node.js', 'PostgreSQL', 'MongoDB'] },
		{ name: 'Tools', icon: Globe, items: ['Git', 'Docker', 'Vercel'] }
	];
</script>

<section id="about" class="py-20 bg-slate-800/50">
	<div class="container mx-auto px-6">
		<div class="max-w-6xl mx-auto">
			<h2 class="text-4xl md:text-5xl font-bold text-center text-white mb-16">
				About <span class="text-transparent bg-clip-text bg-gradient-to-r from-purple-400 to-pink-400">Me</span>
			</h2>

			<div class="grid md:grid-cols-2 gap-12 items-center mb-16">
				<div>
					<h3 class="text-2xl font-bold text-white mb-6">My Story</h3>
					<p class="text-gray-300 mb-4 leading-relaxed">
						I'm a passionate full-stack developer with over 5 years of experience creating 
						digital experiences that combine beautiful design with robust functionality.
					</p>
					<p class="text-gray-300 mb-6 leading-relaxed">
						I love turning complex problems into simple, beautiful solutions. When I'm not 
						coding, you'll find me exploring new technologies, contributing to open source 
						projects, or sharing knowledge with the developer community.
					</p>
					<a 
						href="/resume.pdf" 
						class="inline-flex items-center bg-gradient-to-r from-purple-600 to-blue-600 text-white px-6 py-3 rounded-lg hover:from-purple-700 hover:to-blue-700 transition-all"
					>
						Download Resume
					</a>
				</div>

				<div class="grid grid-cols-2 gap-6">
					{#each skills as skill}
						<div class="relative bg-slate-800/50 p-6 rounded-xl border border-slate-700
    overflow-hidden group transition-all duration-300
    hover:border-purple-500">
	<div class="absolute inset-0 bg-gradient-to-br from-purple-600/20 to-blue-600/20
                transform translate-y-full group-hover:translate-y-0 transition-transform duration-500 ease-in-out">
    </div>
							<svelte:component this={skill.icon} class="text-purple-400 mb-4" size={32} />
							<h4 class="text-white font-bold mb-3">{skill.name}</h4>
							<ul class="text-gray-400 text-sm space-y-1">
								{#each skill.items as item}
									<li>{item}</li>
								{/each}
							</ul>
						</div>
					{/each}
				</div>
			</div>
		</div>
	</div>
</section>
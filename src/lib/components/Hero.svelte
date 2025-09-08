<script>
	import { Github, Linkedin, Mail, ChevronDown } from 'lucide-svelte';
	import { onMount } from 'svelte';

	let heroElement;
	let isVisible = false;

	onMount(() => {
		isVisible = true;
	});
</script>

<section id="hero" bind:this={heroElement} class=" min-h-screen flex items-center justify-center relative overflow-hidden">
<div class="absolute inset-0 bg-gradient-to-br from-slate-900 via-purple-900 to-blue-950"></div>


    <div class="absolute inset-0 bg-[radial-gradient(circle_at_1px_1px,#ffffff40_1px,transparent_0)] [background-size:24px_24px] opacity-60"></div>
	<div class="container mx-auto px-6 text-center relative z-10">
		<div class="max-w-4xl mx-auto">
			<h1 class="text-5xl md:text-7xl font-bold text-white mb-6 opacity-0 {isVisible ? 'animate-fade-in' : ''}">
    Hi, I'm <span class="
        text-transparent bg-clip-text bg-gradient-to-r 
        from-purple-400 to-pink-400
        hover:from-purple-300 hover:to-pink-300
        transition-all duration-300
    ">Enzo</span>
</h1>
			
			<p class="text-xl md:text-2xl text-gray-300 mb-8 opacity-0 {isVisible ? 'animate-fade-in-delay' : ''}">
				Full-Stack Developer passionate about creating amazing web experiences
			</p>
			
			<div class="flex justify-center space-x-6 mb-12 opacity-0 {isVisible ? 'animate-fade-in-delay-2' : ''}">
				<a href="https://github.com" class="text-gray-400 hover:text-white transition-colors transform hover:scale-110">
					<Github size={28} />
				</a>
				<a href="mailto:your.email@example.com" class="text-gray-400 hover:text-white transition-colors transform hover:scale-110">
					<Mail size={28} />
				</a>
			</div>

			<div class="flex flex-col sm:flex-row gap-4 justify-center opacity-0 {isVisible ? 'animate-fade-in-delay-3' : ''}">
				<a 
					href="#projects" 
					class="bg-gradient-to-r from-purple-600 to-blue-600 text-white px-8 py-3 rounded-full hover:from-purple-700 hover:to-blue-700 transition-all transform hover:scale-105"
				>
					View My Work
				</a>
				<a 
					href="#contact" 
					class="border-2 border-purple-600 text-purple-400 px-8 py-3 rounded-full hover:bg-purple-600 hover:text-white transition-all"
				>
					Get In Touch
				</a>
			</div>
		</div>
	</div>

	<div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce">
		<ChevronDown class="text-gray-400" size={32} />
	</div>
</section>

<style>
	@keyframes fade-in {
		from { opacity: 0; transform: translateY(30px); }
		to { opacity: 1; transform: translateY(0); }
	}

	.animate-fade-in {
		animation: fade-in 0.8s ease-out forwards;
	}

	.animate-fade-in-delay {
		animation: fade-in 0.8s ease-out 0.2s forwards;
	}

	.animate-fade-in-delay-2 {
		animation: fade-in 0.8s ease-out 0.4s forwards;
	}

	.animate-fade-in-delay-3 {
		animation: fade-in 0.8s ease-out 0.6s forwards;
	}
</style>
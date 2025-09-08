<script>
	import { Github, Linkedin, Mail, Heart } from 'lucide-svelte';
</script>

<footer class="bg-gradient-to-r from-slate-900/80 via-purple-950/70 to-slate-900/80 backdrop-blur-sm border-b border-purple-800/50 border-t border-slate-700 py-12">
	<div class="container mx-auto px-6">
		<div class="max-w-6xl mx-auto">
			<div class="flex flex-col md:flex-row justify-between items-center">
				<div class="mb-6 md:mb-0">
					<h3 class="text-2xl font-bold text-white mb-2">Let's Connect</h3>
					<p class="text-gray-400">Building the future, one line of code at a time.</p>
				</div>

				<div class="flex space-x-6">
					<a href="https://github.com" class="text-gray-400 hover:text-white transition-colors">
						<Github size={24} />
					</a>
					<a href="https://linkedin.com" class="text-gray-400 hover:text-white transition-colors">
						<Linkedin size={24} />
					</a>
					<a href="mailto:your.email@example.com" class="text-gray-400 hover:text-white transition-colors">
						<Mail size={24} />
					</a>
				</div>
			</div>

			<div class="border-t border-slate-700 mt-8 pt-8 text-center">
				<p class="text-gray-400 flex items-center justify-center">
					Made with <Heart class="text-red-500 mx-2" size={16} /> using SvelteKit
				</p>
				<p class="text-gray-500 text-sm mt-2">
					© 2024 Your Name. All rights reserved.
				</p>
			</div>
		</div>
	</div>
</footer>
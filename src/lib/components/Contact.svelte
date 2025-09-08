<script>
	import { Mail, MessageSquare, Send } from 'lucide-svelte';

	let formData = {
		name: '',
		email: '',
		message: ''
	};

	let isSubmitting = false;
	let isSubmitted = false;

	async function handleSubmit(event) {
		event.preventDefault();
		isSubmitting = true;

		// Simulate form submission
		await new Promise(resolve => setTimeout(resolve, 1000));
		
		isSubmitting = false;
		isSubmitted = true;
		
		// Reset form after 3 seconds
		setTimeout(() => {
			isSubmitted = false;
			formData = { name: '', email: '', message: '' };
		}, 3000);
	}
</script>

<section id="contact" class="py-20 bg-slate-800/50">
	<div class="container mx-auto px-6">
		<div class="max-w-4xl mx-auto">
			<h2 class="text-4xl md:text-5xl font-bold text-center text-white mb-16">
				Get In <span class="text-transparent bg-clip-text bg-gradient-to-r from-purple-400 to-pink-400">Touch</span>
			</h2>

			<div class="grid md:grid-cols-2 gap-12">
				<div>
					<h3 class="text-2xl font-bold text-white mb-6">Let's work together</h3>
					<p class="text-gray-300 mb-8 leading-relaxed">
						I'm always interested in new opportunities and exciting projects. 
						Whether you have a question, want to collaborate, or just say hi, 
						I'd love to hear from you!
					</p>

					<div class="space-y-4">
						<div class="flex items-center text-gray-300">
							<Mail class="text-purple-400 mr-4" size={20} />
							<span>your.email@example.com</span>
						</div>
						<div class="flex items-center text-gray-300">
							<MessageSquare class="text-purple-400 mr-4" size={20} />
							<span>Open to freelance opportunities</span>
						</div>
					</div>
				</div>

				<form on:submit={handleSubmit} class="space-y-6">
					<div>
						<label for="name" class="block text-white mb-2">Name</label>
						<input 
							type="text" 
							id="name" 
							bind:value={formData.name}
							required
							class="w-full bg-slate-700 border border-slate-600 rounded-lg px-4 py-3 text-white focus:border-purple-500 focus:outline-none transition-colors"
							placeholder="Your Name"
						/>
					</div>

					<div>
						<label for="email" class="block text-white mb-2">Email</label>
						<input 
							type="email" 
							id="email" 
							bind:value={formData.email}
							required
							class="w-full bg-slate-700 border border-slate-600 rounded-lg px-4 py-3 text-white focus:border-purple-500 focus:outline-none transition-colors"
							placeholder="your@email.com"
						/>
					</div>

					<div>
						<label for="message" class="block text-white mb-2">Message</label>
						<textarea 
							id="message" 
							rows="5"
							bind:value={formData.message}
							required
							class="w-full bg-slate-700 border border-slate-600 rounded-lg px-4 py-3 text-white focus:border-purple-500 focus:outline-none transition-colors resize-none"
							placeholder="Tell me about your project..."
						></textarea>
					</div>

					<button 
						type="submit" 
						disabled={isSubmitting || isSubmitted}
						class="w-full bg-gradient-to-r from-purple-600 to-blue-600 text-white py-3 rounded-lg hover:from-purple-700 hover:to-blue-700 transition-all disabled:opacity-50 disabled:cursor-not-allowed flex items-center justify-center"
					>
						{#if isSubmitting}
							Sending...
						{:else if isSubmitted}
							Message Sent!
						{:else}
							<Send size={18} />
							<span class="ml-2">Send Message</span>
						{/if}
					</button>
				</form>
			</div>
		</div>
	</div>
</section>
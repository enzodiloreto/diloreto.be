<script>
	import { Menu, X } from 'lucide-svelte';
	let mobileMenuOpen = false;

	const navItems = [
		{ name: 'Home', href: '#hero' },
		{ name: 'About', href: '#about' },
		{ name: 'Projects', href: '#projects' },
		{ name: 'Contact', href: '#contact' }
	];
</script>

<header class="fixed top-0 w-full bg-gradient-to-r from-slate-900/80 via-purple-950/70 to-slate-900/80 backdrop-blur-sm border-b border-purple-800/50 z-50">
	<nav class="container mx-auto px-6 py-4">
		<div class="flex justify-between items-center">
			<a href="/" class="text-2xl font-bold">
    <span class="
        text-transparent bg-clip-text bg-gradient-to-r 
        from-purple-400 to-pink-400 
        hover:from-purple-300 hover:to-pink-300
        transition-all duration-300
    ">
        Diloreto.be
    </span>
	
</a>
			<!-- Desktop Navigation -->
	<div class="hidden md:flex space-x-8">
    {#each navItems as item}
        <a 
            href={item.href} 
            class="text-gray-300 hover:text-white transition-colors px-3 py-2 rounded-md hover:bg-white/10"
        >
            {item.name}
        </a>
    {/each}
</div>

			<!-- Mobile Menu Button -->
			<button 
				class="md:hidden text-white"
				on:click={() => mobileMenuOpen = !mobileMenuOpen}
			>
				{#if mobileMenuOpen}
					<X size={24} />
				{:else}
					<Menu size={24} />
				{/if}
			</button>
		</div>

		<!-- Mobile Navigation -->
		{#if mobileMenuOpen}
			<div class="md:hidden mt-4 pb-4">
				{#each navItems as item}
					<a 
						href={item.href} 
						class="block py-2 text-gray-300 hover:text-white transition-colors"
						on:click={() => mobileMenuOpen = false}
					>
						{item.name}
					</a>
				{/each}
			</div>
		{/if}
	</nav>
</header>
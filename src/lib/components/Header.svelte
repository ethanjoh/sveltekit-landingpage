<script>
  let isMenuOpen = $state(false);

  function toggleMenu() {
    isMenuOpen = !isMenuOpen;
  }

  function closeMenu() {
    isMenuOpen = false;
  }
</script>

<header class="sticky top-0 z-50 backdrop-blur-md bg-white/80 border-b border-gray-100">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex justify-between items-center h-16">
      <!-- Logo -->
      <a href="/" class="flex-shrink-0 flex items-center" onclick={closeMenu}>
        <span class="text-2xl font-bold text-gray-900 tracking-tight">AURA</span>
      </a>
      
      <!-- Desktop Navigation -->
      <nav class="hidden md:flex space-x-8">
        <a href="/about" class="text-gray-700 hover:text-black font-medium transition-colors">소개</a>
        <a href="/product" class="text-gray-700 hover:text-black font-medium transition-colors">제품</a>
      </nav>

      <!-- Mobile menu button -->
      <div class="flex items-center md:hidden">
        <button type="button" aria-label="Menu" class="text-gray-500 hover:text-gray-900 focus:outline-none" onclick={toggleMenu}>
          <svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            {#if isMenuOpen}
              <!-- X icon when menu is open -->
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
            {:else}
              <!-- Hamburger icon when menu is closed -->
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
            {/if}
          </svg>
        </button>
      </div>
    </div>
  </div>

  <!-- Mobile Navigation Menu -->
  {#if isMenuOpen}
    <div class="md:hidden bg-white border-t border-gray-100 shadow-lg absolute w-full">
      <div class="px-4 pt-2 pb-4 space-y-2 sm:px-6 flex flex-col">
        <a href="/about" class="block px-3 py-3 rounded-md text-base font-medium text-gray-700 hover:text-black hover:bg-gray-50" onclick={closeMenu}>소개</a>
        <a href="/product" class="block px-3 py-3 rounded-md text-base font-medium text-gray-700 hover:text-black hover:bg-gray-50" onclick={closeMenu}>제품</a>
      </div>
    </div>
  {/if}
</header>

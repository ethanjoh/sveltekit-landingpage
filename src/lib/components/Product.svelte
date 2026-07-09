<script>
  import { productData } from '../data/productData.js';
  let { showSpecs = false } = $props();
</script>

<section id="product" class="scroll-mt-16 py-24 bg-white">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    
    <div class="lg:grid lg:grid-cols-2 lg:gap-16 items-center">
      <!-- Product Image -->
      <div class="mb-12 lg:mb-0">
        <div class="rounded-3xl overflow-hidden shadow-2xl bg-gray-50">
          <img src={productData.imageUrl} alt={productData.name} class="w-full h-auto object-cover" loading="lazy">
        </div>
      </div>
      
      <!-- Product Info -->
      <div>
        <h2 class="text-4xl font-extrabold text-gray-900 mb-4">{productData.name}</h2>
        <p class="text-xl text-gray-500 mb-8">{productData.summary}</p>
        
        <div class="mb-8">
          <span class="text-5xl font-bold text-gray-900">{productData.price}</span>
        </div>

        <!-- Specs Grid -->
        <div class="grid grid-cols-1 sm:grid-cols-2 gap-6 mb-10">
          {#each productData.features as feature}
            <div class="bg-gray-50 p-6 rounded-2xl">
              <h3 class="text-lg font-semibold text-gray-900 mb-2">{feature.title}</h3>
              <p class="text-gray-600">{feature.description}</p>
            </div>
          {/each}
        </div>

        <!-- CTA -->
        <button class="w-full sm:w-auto flex items-center justify-center px-8 py-4 border border-transparent text-lg font-medium rounded-full text-white bg-black hover:bg-gray-800 transition-colors shadow-lg">
          지금 구매하기
        </button>
      </div>
    </div>
    
    <!-- Technical Specifications -->
    {#if showSpecs}
    <div class="mt-24 border-t border-gray-200 pt-16">
      <h3 class="text-3xl font-bold text-gray-900 mb-10 text-center">상세 스펙</h3>
      <div class="max-w-3xl mx-auto bg-gray-50 rounded-2xl overflow-hidden shadow-sm border border-gray-100">
        <dl class="divide-y divide-gray-200">
          {#each productData.specs as spec}
            <div class="px-6 py-5 sm:grid sm:grid-cols-3 sm:gap-4 sm:px-8 hover:bg-gray-100 transition-colors">
              <dt class="text-sm font-medium text-gray-500">{spec.label}</dt>
              <dd class="mt-1 text-sm text-gray-900 sm:mt-0 sm:col-span-2">{spec.value}</dd>
            </div>
          {/each}
        </dl>
      </div>
    </div>
    {/if}
    
  </div>
</section>

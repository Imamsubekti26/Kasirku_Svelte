<script>
  export let styleType = 'fill'
  export let isLoading = false
  let looks
  switch (styleType) {
    case 'outline':
      looks = 'text-blue-400 bg-white border border-blue-400'
      break;
    case 'danger':
      looks = 'text-red-400 bg-white border border-red-400'
      break;
    default:
      looks = 'text-white bg-blue-400'
      break;
  }
</script>

<button 
    class="w-full px-2.5 py-3 rounded-md text-xs flex items-center justify-center {looks}"
    on:click
    disabled={isLoading}
  >
    {#if isLoading}
      <svg class="animate-spin -ml-1 mr-3 h-5 w-5 text-white" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
        <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
        <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
      </svg>
    {/if}
    <slot />
</button>
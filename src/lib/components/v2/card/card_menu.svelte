<script>
  export let product
  $: name = product.name
  $: image = product.image
  $: price = product.price
</script>

<div class="flex flex-col gap-6 mb-6">
  <div class="flex justify-between px-6">
    <div class="flex gap-4 w-full">
      <img src={image} alt="food" class="object-cover h-20 w-20 rounded-lg">
      <div class="flex flex-col justify-between h-full w-full">
        <p class="text-base font-medium text-left text-black" > {name} </p>
        <div class="flex justify-between items-end">
          <p class="text-xs text-left text-black"> {price} </p>
          <div class="flex gap-2 items-center"><slot /></div>
        </div>
      </div>
    </div>
  </div>
  <hr class="w-full">
</div>
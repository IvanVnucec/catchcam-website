<script context="module">
  import Product from "$lib/components/Product.svelte";
  import NoteCard from "$lib/components/NoteCard.svelte";

  import CommaPrimeSIMImage from "$lib/images/products/comma-prime-sim/comma-prime-sim.jpg";
  import CommaPrimeSIMInstallationImage from "$lib/images/products/comma-prime-sim/comma-prime-sim-installation.png";

  export const productInfo = {
    title: "comma prime SIM",
    id: "gid://shopify/Product/1923405250623",
    route: "/shop/comma-prime-sim",
    category: "accessories",
    price: "$20",
    images: [CommaPrimeSIMImage, CommaPrimeSIMInstallationImage],
  };
</script>

<script>
  export let product;
</script>

<Product {product}>
  <div slot="notes">
    <NoteCard title="Product Compatibility">This product is only for the comma 3/3X.</NoteCard>
    <NoteCard title="Note">
      For US customers only, requires $24/month comma prime subscription you can purchase at
      <a href="http://connect.comma.ai/" target="_blank">connect.comma.ai</a>.
    </NoteCard>
  </div>

  <div slot="description">
    <strong>Description</strong>
    <p>
      This is a replacement for the SIM that ships with the comma 3X to support <a href="/connect">comma prime</a>.
    </p>
    <p>
      See how to replace the SIM card in a comma 3/3X
      <a href="/support#how-do-you-replace-the-sim-card-in-a-comma-3x" target="_blank">here</a>.
    </p>
  </div>
</Product>

<script>
  let product = {
    id: "",
    name: "",
    description: "",
    category: "",
    imageURL: "",
  };

  const onSubmitHandler = (e) => {
    e.preventDefault();
    console.log(e);
  };
</script>

<main>
  <form on:submit={onSubmitHandler}>
    <input
      bind:value={product.name}
      type="text"
      placeholder="Product Name"
      id="product-name"
    />
    <textarea
      bind:value={product.description}
      name="product-description"
      id="product-image-url"
      rows="3"
      placeholder="Product Description"
    ></textarea>
    <input
      bind:value={product.imageURL}
      type="url"
      id="product-image-url"
      placeholder="https://faztweb.com/"
    />
    <select bind:value={product.category} id="category">
      <option value="laptops">Laptops</option>
      <option value="peripherials">Peripherials</option>
      <option value="Servers">Servers</option>
    </select>

    <button>Save Product</button>
  </form>
</main>

<style>
</style>

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
  <div class="container">
    <div class="row">
      <div class="col-md-6"><!--card--></div>
      <div class="col-md-6">
        <div class="card">
          <div class="card-body">
            <form on:submit={onSubmitHandler}>
              <input
                bind:value={product.name}
                type="text"
                placeholder="Product Name"
                id="product-name"
                class="form-control"
              />
              <textarea
                bind:value={product.description}
                name="product-description"
                id="product-image-url"
                rows="3"
                placeholder="Product Description"
                class="form-control"
              ></textarea>
              <input
                bind:value={product.imageURL}
                type="url"
                id="product-image-url"
                placeholder="https://faztweb.com/"
                class="form-control"
              />
              <select
                bind:value={product.category}
                id="category"
                class="form-control"
              >
                <option value="laptops">Laptops</option>
                <option value="peripherials">Peripherials</option>
                <option value="Servers">Servers</option>
              </select>

              <button>Save Product</button>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</main>

<style>
</style>

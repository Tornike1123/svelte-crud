<script>
  let products = [
    {
      id: 1,
      name: "HP Paviliont Notebook",
      description: "HP Laptop",
      category: "laptop",
    },
    {
      id: 2,
      name: "MacBook",
      description: "MacBook Pro 16",
      category: "peripherials",
    },
  ];

  let product = {
    id: "",
    name: "",
    description: "",
    category: "",
    imageURL: "",
  };

  const onSubmitHandler = (e) => {
    const newProduct = {
      id: product.lenght,
      name: product.name,
      description: product.description,
      category: product.category,
      imageURL: product.imageURL,
    };

    products = products.concat(newProduct);

    cleanProdut();
  };

  const cleanProdut = () => {
    product = {
      id: "",
      name: "",
      description: "",
      category: "",
      imageURL: "",
    };
  };
</script>

<main>
  <div class="container">
    <div class="row">
      <div class="col-md-6">
        {#each products as product}
          <div class="card mt-2">
            <div class="row">
              <div class="col-md-4">
                {#if !product.imageURL}
                  <img
                    src="/image/no_products.png"
                    alt="img"
                    class="img-fluid p-2"
                  />
                {:else}
                  <!-- svelte-ignore a11y-img-redundant-alt -->
                  <img
                    src={product.imageURL}
                    alt="image"
                    class="img-fluid p-2"
                  />
                {/if}
              </div>
              <div class="col-md-8">
                <div class="card-body">
                  <h5>
                    <strong>{product.name}</strong>
                    <span>
                      <small>
                        {product.category}
                      </small>
                    </span>
                  </h5>
                  <p class="card-text">{product.description}</p>
                  <button class="btn btn-danger"> Delete </button>
                  <button class="btn btn-secondary"> Edit </button>
                </div>
              </div>
            </div>
          </div>
        {/each}
      </div>
      <div class="col-md-6">
        <div class="card">
          <div class="card-body">
            <form on:submit|preventDefault={onSubmitHandler}>
              <div class="form-group">
                <input
                  bind:value={product.name}
                  type="text"
                  placeholder="Product Name"
                  id="product-name"
                  class="form-control"
                  required={true}
                />
              </div>
              <div class="form-group">
                <textarea
                  bind:value={product.description}
                  name="product-description"
                  id="product-image-url"
                  rows="3"
                  placeholder="Product Description"
                  class="form-control"
                ></textarea>
              </div>
              <div class="form-group">
                <input
                  bind:value={product.imageURL}
                  type="url"
                  id="product-image-url"
                  placeholder="https://faztweb.com/"
                  class="form-control"
                />
              </div>
              <div class="form-group">
                <select
                  bind:value={product.category}
                  id="category"
                  class="form-control"
                >
                  <option value="laptops">Laptops</option>
                  <option value="peripherials">Peripherials</option>
                  <option value="Servers">Servers</option>
                </select>
              </div>

              <button class="btn btn-secondary">Save Product</button>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</main>

<style>
</style>

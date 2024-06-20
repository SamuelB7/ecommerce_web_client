<script lang="ts">
    import { FindAllProductsDocument, type Product } from "$lib/graphql/types";
    import { GraphQLClient } from "graphql-request";
    import { onMount } from "svelte";
    import { writable } from "svelte/store";

    let products = writable<Product[]>([]);

    onMount(async () => {
        const client = new GraphQLClient(import.meta.env.VITE_GRAPHQL_API);

        const { findAllProducts } = await client.request(
            FindAllProductsDocument,
        );

        if (findAllProducts) {
            console.log("ALL PRDUCTS: ", findAllProducts);
        }

        products.set(findAllProducts.products);
    });
</script>

<div>
    <h2>All Products</h2>
    <ul>
        {#each $products as product}
            <li>{product.name} - ${product.price}</li>
        {:else}
            <p>Loading...</p>
        {/each}
    </ul>
</div>

<script lang="ts">
    import Carousel from "../components/Carousel.svelte";
    import Header from "../components/Header.svelte";
    import Hero from "../components/Hero.svelte";
    import ProductCard from "../components/ProductCard.svelte";

    const products = [
        {
            name: "Product 1",
            description:
                "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
            image: "https://place-hold.it/500x500",
            price: 19.99,
        },
        {
            name: "Product 2",
            description:
                "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
            image: "https://place-hold.it/500x500",
            price: 24.95,
        },
        {
            name: "Product 3",
            description:
                "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
            image: "https://place-hold.it/500x500",
            price: 24.95,
        },
        {
            name: "Product 4",
            description:
                "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
            image: "https://place-hold.it/500x500",
            price: 24.95,
        },
        {
            name: "Product 5",
            description:
                "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
            image: "https://place-hold.it/500x500",
            price: 24.95,
        },
    ];
</script>

<Header />
<Hero />
<Carousel>
    {#each products as product}
        <ProductCard {product} />
    {/each}
</Carousel>

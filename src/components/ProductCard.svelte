<script lang="ts">
    type ProductCardProps = {
        name: string;
        description: string;
        image: string;
        price: number;
    };
    export let product: ProductCardProps;
</script>

<div class="w-[350px] rounded-2xl shadow-lg">
    <img
        class="w-full rounded-tl-2xl rounded-tr-2xl"
        src={product.image}
        alt={product.name}
    />
    <div class="flex items-center">
        <div class="px-6 py-4">
            <div class="font-bold text-xl mb-2">{product.name}</div>
            <p class="text-slate-700 text-base">
                {product.description}
            </p>
        </div>
        <div class="px-6 pt-4 pb-2">
            <span
                class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
                >${product.price}</span
            >
        </div>
    </div>
    <div class="px-6 py-4">
        <button
            class="flex items-center justify-center p-4 rounded-3xl bg-slate-950 text-white"
            >Order Now</button
        >
    </div>
</div>

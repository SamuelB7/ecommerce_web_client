<script>
    import cartIcon from "$lib/assets/shopping-cart.svg";
    import userIcon from "$lib/assets/user.svg";
</script>

<header>
    <div class="flex items-center justify-between py-5 px-40">
        <div class="flex items-center gap-8">
            <a href="/">Logo</a>
            <div class="w-[2px] h-10 bg-slate-700"></div>
            <a href="/">Home</a>
            <a href="/products">Products</a>
            <a href="/about">About Us</a>
            <a href="/contact">Contact</a>
        </div>
        <div class="flex justify-center items-center gap-8">
            <a href="/cart">
                <img src={cartIcon} alt="shopping-cart-icon" />
            </a>
            <a href="/my-area">
                <img src={userIcon} alt="user-icon" />
            </a>
        </div>
    </div>
</header>

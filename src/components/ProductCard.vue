<template>
    <div class="product-card">

        <!-- Product Image -->
        <div class="image-wrapper">
            <img
                v-if="image"
                :src="image"
                :alt="name"
                class="product-image"
            />

            <div v-else class="no-image">
                No Image
            </div>
        </div>

        <!-- Product Information -->
        <div class="product-info">

            <h2 class="product-name">
                {{ name }}
            </h2>

            <p class="product-price">
                ${{ price.toFixed(2) }}
            </p>

            <button class="buy-btn">
                Buy Now
            </button>

        </div>

    </div>
</template>

<script setup>

defineProps({
    name: {
        type: String,
        required: true
    },

    price: {
        type: Number,
        required: true
    },

    image: {
        type: String,
        required: false
    }
})

</script>

<style scoped>

.product-card {
    width: 280px;
    overflow: hidden;
    background: #ffffff;
    border: 1px solid #e5e7eb;
    border-radius: 16px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
    transition: all 0.3s ease;
}

.product-card:hover {
    transform: translateY(-6px);
    box-shadow: 0 12px 25px rgba(0, 0, 0, 0.12);
}

/* Image */

.image-wrapper {
    width: 100%;
    height: 220px;
    background: #f8f9fa;
    display: flex;
    justify-content: center;
    align-items: center;
    overflow: hidden;
}

.product-image {
    width: 100%;
    height: 100%;
    object-fit: contain;
    padding: 15px;
    transition: transform 0.3s ease;
}

.product-card:hover .product-image {
    transform: scale(1.08);
}

.no-image {
    color: #999;
    font-size: 14px;
}

/* Product Info */

.product-info {
    padding: 20px;
}

.product-name {
    margin: 0 0 10px;
    font-size: 20px;
    font-weight: 600;
    color: #222;
}

.product-price {
    margin: 0 0 18px;
    font-size: 22px;
    font-weight: 700;
    color: #dc6868;
}

/* Button */

.buy-btn {
    width: 100%;
    padding: 11px 15px;
    border: none;
    border-radius: 8px;
    background: #dc6868;
    color: white;
    font-size: 15px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.2s ease;
}

.buy-btn:hover {
    background: #c95252;
}

.buy-btn:active {
    transform: scale(0.98);
}

</style>

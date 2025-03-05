<template>
    <div>
        <!-- remove $event is the id (passed in CartListItem $emit)-->
        <!-- update $event is the JS object {id, newQuantity} passed in CartListItem $emit -->
        <CartListItem 
            v-for="cartItem in cartItems"
            :key="cartItem.id"
            :item="cartItem"
            @item-remove="$emit('item-remove', $event)"
            @quantity-update="$emit('quantity-update', $event)"
        ></CartListItem>
    </div>
</template>

<script setup>
import CartListItem from '@/components/CartListItem.vue'

defineProps(['cartItems'])
defineEmits(['item-remove', 'quantity-update'])
</script>

<style scoped>

</style>
<template>
  <div
    class="w-full px-8 h-fit py-[2rem] bg-bgPrimary flex flex-col gap-4 items-center rounded-xl"
  >
    Total Bill: ${{ cartTotal }}
    <button
      :disabled="cartTotal === 0"
      @click="
        () => {
          router.push('/checkout');
        }
      "
      :class="`${
        cartTotal === 0 && 'opacity-50'
      } w-full bg-buttonPrimary text-center px-4 py-1 rounded-full`"
    >
      Checkout
    </button>
  </div>
</template>

<script setup lang="ts">
import { useCart } from "~/composables/Cart";
const { cartTotal } = useCart();
const router = useRouter();
</script>

<template>
    <MainLayout>
        <div id="RestaurantPage" class="mt-4 max-w-[1200px] mx-auto px-2">
            <div class=" mx-auto w-full">
                <div class="w-full">
                    <img 
                        class="rounded-lg object-fit w-full h-[40vh]"
                        src="https://picsum.photos/id/212/800/800" 
                    >
                </div>
            </div>
            <div class="w-full bg-white p-3 mt-3 rounded-lg">
                <div v-if="true">
                    <p class="mb-2">Title</p>
                    <p class="font-light text-[12px] mb-2">Description Section</p>
                </div>
                <div class="flex items-center pt-1.5">
                    <span class="h-4 min-w-4 rounded-full p-0.5 bg-[#FFD000] mr-2">
                        <Icon name="material-symbols:star-rounded" class="-mt-[17px]" size="12" />
                    </span>
                    <p class="text-[#FF5353]">Free Delivery</p>
                </div>

                <div class="flex items-center justify-start my-2">
                    <Icon name="ic:baseline-star" color="#FF5353" />
                    <Icon name="ic:baseline-star" color="#FF5353" />
                    <Icon name="ic:baseline-star" color="#FF5353" />
                    <Icon name="ic:baseline-star" color="#FF5353" />
                    <Icon name="ic:baseline-star" color="#FF5353" />
                    <span class="text-[13px] font-light ml-2">5 213 Reviews 1,000+ orders</span>
                </div>

                <div class="border-b" />

                <div class="flex items-center justify-start gap-2 my-2">
                    <p class="text-xl font-bold text-[#FF5353]">Burgers</p>
                    <!-- <span class="bg-[#F5F5F5] border text-[#C08562] text-[9px] font-semibold px-1.5 rounded-sm">70% off</span> -->
                </div>

                <div class="flex items-center justify-start gap-10 my-2">
                    <div class="text-xl font-bold">{{ MenuTitle }}</div>
                    <div class="text-xl font-bold">SR {{ priceComputed }}</div>
                    <!-- <span class="bg-[#F5F5F5] border text-[#C08562] text-[9px] font-semibold px-1.5 rounded-sm">70% off</span> -->
                    <div class="">
                        <button
                        @click="addToCart()"
                        :disabled="isInCart"
                        class="
                            px-6
                            py-2
                            rounded-lg
                            text-white
                            text-lg
                            font-semibold
                            bg-gradient-to-r
                            from-[#FF851A]
                            to-[#FFAC2C]
                        "
                        >
                            <div v-if="isInCart">Is Added</div>
                            <div v-else>Add to Cart</div>
                        </button>
                    </div>
                    
                </div>

                <p class="text-[#009A66] text-xs font-semibold pt-1">
                    Free Delivery minimum of SR 200 order
                </p>

                <div class="py-2" />

                <!-- <button
                    @click="addToCart()"
                    :disabled="isInCart"
                    class="
                        px-6
                        py-2
                        rounded-lg
                        text-white
                        text-lg
                        font-semibold
                        bg-gradient-to-r
                        from-[#FF851A]
                        to-[#FFAC2C]
                    "
                >
                    <div v-if="isInCart">Is Added</div>
                    <div v-else>Add to Cart</div>
                </button> -->
            </div>
        </div>
    </MainLayout>
</template>

<script setup>
import MainLayout from '~/layouts/MainLayout.vue';
import { useUserStore } from '~/stores/user';
const userStore = useUserStore()

const route = useRoute()

const isInCart = computed(() => {
    let res = false
    userStore.cart.forEach(prod => {
        if(route.params.id == prod.id) {
            res = true
        }
    })
    return res
})

const MenuTitle = computed(() => {
    return 'Cheese Burger'
})

const priceComputed = computed(() => {
    return '26.40'
})


const addToCart = () => {
    alert('ADDED')
}

</script>

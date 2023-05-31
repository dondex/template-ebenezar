<template>
    <div
        :id="`RestaurantComponent${restaurant.id}`"
        class="
            bg-white
            inline-block
            rounded
            hover:shadow-[0_0_10px_3px_rgba(0,0,0,0.15)]
            cursor-pointer
        "
    >
        <NuxtLink :to="`/restaurant/${restaurant.id}`">
            <img 
                class="rounded-t"
                :src="restaurant.url"
            >       

            <div id="RestaurantDetails">

                <p class="px-1 pb-1">
                    <span class="text-[#009A66] text-xs font-semibold">{{ restaurant.title.substring(0,60) }}</span>
                </p>

            </div>
        </NuxtLink>
    </div>
</template>

<script setup>
const props = defineProps(['restaurant'])
const { restaurant } = toRefs(props)


</script>


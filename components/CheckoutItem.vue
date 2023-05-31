<template>
    <div class="flex justify-start my-2"> 

        <img
            class="rounded-md md:w-[150px] w-[90px]"
            :src="menu.url"
        >

        <div class="overflow-hidden pl-2">
            <div class="flex items-center">
                <span class=" bg-[#FD374F] text-white text-[9px] font-semibold px-1.5 roudned-sm min-w-[80px]">Delicious Foods</span>
                <div class="truncate pl-2">{{ menu.title }}</div>
            </div>

            <div class="text-lg font-semibold mt-2">
                    SR <span class="font-bold">{{ menu.price / 100 }}</span>
            </div>
        </div>
        
    </div>
</template>

<script setup>

const props = defineProps(['menu'])
const { menu } = toRefs(props)

</script>


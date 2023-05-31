<template>
    <MainLayout>
        <div id="IndexPage" class="mt-4 max-w-[1200px] mx-auto px-2">
            <div id="IndexPage" class="mt-4 max-w-[1200px] mx-auto px-2">
                <div class="grid xl:grid-cols-6 lg:grid-cols-5 md:grid-cols-4 sm:grid-cols-3 grid-cols-2 gap-4">
                    <!-- <div v-if="menus" v-for="menu in menus" :key="menu">
                        <MenuComponent :menu="menu" />
                    </div> -->
                    <div v-if="restaurants" v-for="restaurant in restaurants" :key="restaurant">
                        <RestaurantComponent :restaurant="restaurant" />
                    </div>
                </div>
            </div>
        </div>
    </MainLayout>
</template>

<script setup>
    import MainLayout from '~/layouts/MainLayout.vue';

    const restaurants = [
        { id: 1, title: "Jollibee", description: "This is a description", url:"https://picsum.photos/id/7/800/800" },
        { id: 2, title: "Mcdo", description: "This is a description", url:"https://picsum.photos/id/8/800/800" },
        { id: 3, title: "KFC", description: "This is a description", url:"https://picsum.photos/id/99/800/800" },
        { id: 4, title: "Shakeys", description: "This is a description", url:"https://picsum.photos/id/10/800/800" },
        { id: 5, title: "Angel Burger", description: "This is a description", url:"https://picsum.photos/id/11/800/800" },
        { id: 6, title: "Krispy Kreme", description: "This is a description", url:"https://picsum.photos/id/12/800/800" },
        { id: 7, title: "Dunkin Donut", description: "This is a description", url:"https://picsum.photos/id/13/800/800" },
        { id: 8, title: "Mang Inasal", description: "This is a description", url:"https://picsum.photos/id/14/800/800" },
        { id: 9, title: "Siomai King", description: "This is a description", url:"https://picsum.photos/id/15/800/800" },
        { id: 10, title: "Burger King", description: "This is a description", url:"https://picsum.photos/id/16/800/800" },
    ]
</script>


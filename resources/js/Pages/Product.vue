<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import {Head} from '@inertiajs/vue3'
import { toRefs } from 'vue';
import MapMarkerOutlineIcon from 'vue-material-design-icons/MapMarkerOutline.vue'
const props=defineProps({product:Object})
const {product}=toRefs(props)

</script>

<template>
<Head title="Product"/>
<AuthenticatedLayout>
    <div class="mt-16"></div>

    <div class="max-w-[1200px] mx-auto flex gap-4 justify-between">
        <div class="w-2/5">
        <img :src="product.image">
       
        </div>

        <div class="w-2/5">
        <div class="text-xl font-extrabold border-b border-b-gray-300 mb-2 pb-2">{{product.tite}}</div>
        <div>
            <div class="text-lg font-extrabold m-1">About this item</div>
            <div>{{product.description}}</div>
        </div>
        </div>

        <div class="w-1/5">
        <div class="border border-gray-300 rounded-lg">
            <div class="my-2 mx-3 mb-2">
                <div class="flex items-center justify-center border-b border-gray-300 pb-1">
                    <Link href="/"
                    class="flex items-center  text-xs font-extrabold text-teal-500 hover:text-red-800 cursor-pointer">
                    <MapMarkerOutlineIcon :size="17"/>Delivery To FirstName -Postcode
                    </Link>

                    <Link 
                         :href="route('login')"
                         class="flex items-center text-xs font-extrabold text-teal-700 hover:text-red-600"
                       >
                       Sign
                    </Link>

                </div>

                <div class="flex items-center justify-center pt-2">
                    <div class="text-red-600 text-sm font-bold">{{product.price}}</div>
                    <button class="bg-yellow-400 px-2 font-bold text-sm rounded-lg border shadow-sm cursor-pointer">
                        <!-- <span>Item Added</span> -->
                        <span>Add To Cart</span>
                    </button>

                </div>
            </div>
        </div>
        </div>

        
    </div>
</AuthenticatedLayout>
    
</template>
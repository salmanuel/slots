<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import Card from '@/Components/Card.vue';
import { Head } from '@inertiajs/vue3';


const comp_accessories = [
    {
        id: 1,
        name: 'Headphone',
        thumbnail: 'https://www.sony.com.ph/image/8f499d4640b363762e66edd1a4916a10?fmt=pjpeg&bgcolor=FFFFFF&bgc=FFFFFF&wid=2515&hei=1320',
        price: '7,499.00 Php'
    },
    {
        id: 2,
        name: 'Mouse',
        thumbnail: 'https://www.officewarehouse.com.ph/__resources/_web_data_/products/products/images/6676.jpg',
        price: '415.00 Php'
    },
];
</script>

<template>
    <Head title="Dashboard" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">Dashboard</h2>
        </template>

        <div class="flex flex-col gap-8 items-center justify-center">
            <div class="max-w-7xl sm:px-6 lg:px-8">
                <div class="bg-gray-200 flex justify-between overflow-hidden shadow-sm sm:rounded-lg mt-8">
                    <div class="grid1 mx-auto">
                        <div v-for="comp_accessory in comp_accessories" :key="comp_accessory.id" class="m-3 bg-gray-900 text-gray-100 rounded-lg">
                            <Card>
                                    <template v-slot:header>
                                        <h1 class="2xl flex justify-center">{{ comp_accessory.name }}</h1>
                                    </template>
                                    <template v-slot:default>
                                        <div>
                                            <img :src="comp_accessory.thumbnail" alt="" style="width: 320px; height:220px;">
                                        </div>
                                    </template>
                                    <template v-slot:content1>
                                        <h1 class="2xl flex justify-center text-gray-900">{{ comp_accessory.price }}</h1>
                                    </template>
                                    <template v-slot:footer >
                                        <!-- <h1 class="2xl flex justify-center">{{ comp_accessory.name }}</h1> -->
                                        <div class="flex justify-center">
                                            <button class="p-2 rounded shadow-md hover:bg-gray-900 hover:text-white">
                                                Buy Now
                                            </button>
                                        </div>

                                    </template>
                            </Card>
                        </div>
                    </div>
                </div>
            </div>

            <div v-for="comp_accessory in comp_accessories" :key="comp_accessory.id" class="bg-gray-200 rounded-lg shadow-lg max-w-2xl">
                <div class="columns-3 gap-y-3 mt-4">
                    <Card class="py-12 ">
                        <template v-slot:header>
                            <h1 class="text-4xl ml-10 font-serif uppercase">Sale!</h1>
                        </template>
                        <template v-slot:default>
                            <div class>
                                <img :src="comp_accessory.thumbnail" alt="" class="w-full aspect-square rounded ">
                            </div>
                        </template>
                        <template v-slot:content1>
                            <div class="mt-4">
                                <h1 class="2xl flex justify-center text-gray-900">For SALE {{ comp_accessory.name }}, Buy now for only {{ comp_accessory.price }}.</h1>
                            </div>
                        </template>
                        <template v-slot:footer>
                            <button class="flex justify-center p-2 rounded shadow-md shadow-gray-500/50 hover:bg-gray-900 hover:text-white mt-12">
                            Buy Now
                            </button>
                        </template>
                    </Card>
                </div>
                
            </div>
            
        </div>
        <div class="max-w-7xl sm:px-6 lg:px-8 flex mx-auto mt-8 mb-8">
            <table class="w-full bg-gray-200 border-collapse sm:rounded-lg">
              <thead>
                <tr class="bg-gray-900 text-gray-100">
                  <th class="p-3">Accessory Name</th>
                  <th class="p-3">Thumbnail</th>
                  <th class="p-3">Price</th>
                  <th class="p-3">Actions</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="comp_accessory in comp_accessories" :key="comp_accessory.id" class="">
                  <td>
                    <Card>
                      <template v-slot:header>
                        <h1 class="2xl flex justify-center">{{ comp_accessory.name }}</h1>
                      </template>
                    </Card>
                  </td>
                  <td>
                    <Card>
                      <template v-slot:default>
                        <div class="flex justify-center">
                          <img :src="comp_accessory.thumbnail" alt="" style="width: 80px; height: 80px;" class="rounded-full">
                        </div>
                      </template>
                    </Card>
                  </td>
                  <td>
                    <Card>
                      <template v-slot:content1>
                        <h1 class="2xl flex justify-center text-gray-900">{{ comp_accessory.price }}</h1>
                      </template>
                    </Card>
                  </td>
                  <td>
                    <Card>
                      <template v-slot:footer>
                        <div class="flex justify-center">
                          <button class="p-2 rounded shadow-md hover:bg-gray-900 hover:text-white">
                            Buy Now
                          </button>
                        </div>
                      </template>
                    </Card>
                  </td>
                </tr>
              </tbody>
            </table>
          </div>
          


    </AuthenticatedLayout>
</template>

<style scoped>
.grid1{
    display: grid;
    grid-template-columns: repeat(3,1fr);
    gap: 24px 24px;
}


</style>

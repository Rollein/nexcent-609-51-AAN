<script setup>
// core version + navigation, pagination modules:
import Swiper from 'swiper';
import { Navigation, Pagination } from 'swiper/modules';
import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';
import { onMounted } from 'vue';
let counter = ref(0)
const manageCards = ref([
  {
    title: 'Membership Organisations',
    subtitle: 'Our membership management software provides full automation of membership renewals and payments',
    imageUrl: '/src/assets/images/manage-1.svg'
  },
  {
    title: 'National Associations',
    subtitle: 'Our membership management software provides full automation of membership renewals and payments',
    imageUrl: '/src/assets/images/manage-2.svg'
  },
  {
    title: 'Clubs & Groups',
    subtitle: 'Our membership management software provides full automation of membership renewals and payments',
    imageUrl: '/src/assets/images/manage-3.svg'
  }
])
onMounted(() =>{// init Swiper:
    
const swiper = new Swiper('.manage-swiper', {
  // configure Swiper to use modules
  modules: [Navigation, Pagination],
   slidesPerView: 1,
            spaceBetween: 10,
            breakpoints: {
                576: {
                    slidesPerView: 1.5,
                    spaceBetween: 24,
                },
                768: {
                    slidesPerView: 3,
                    spaceBetween: 24,
                },
            },

            // If we need pagination
            pagination: {
                el: '.swiper-pagination',
                clickable: true,
            },

            // Navigation arrows
            navigation: {
                nextEl: '.swiper-button-next',
                prevEl: '.swiper-button-prev',
            },
});})
</script>
<template>
        <section class="manage">
            <div class="container">
                <h2>Manage your entire community<br>in a single system</h2>
                <p class="manage__subtitle">Who is Nextcent suitable for?</p>

                <div class="swiper manage-swiper">
                    <div class="swiper-wrapper">

                        <div class="swiper-slide" v-for='(item, id) in manageCards' :key="id">
                            <div class="manage__card h-100">
                                <div class="manage__card-icon">
                                    <img :src="item.imageUrl" alt="item.title">
                                </div>
                                <h4>{{ item.title }}</h4>
                                <p>{{ item.subtitle }}</p>
                            </div>
                        </div>

                    </div>
                    <div class="swiper-pagination"></div>

                    <!-- If we need navigation buttons -->
                    <div class="swiper-button-prev"></div>
                    <div class="swiper-button-next"></div>

                    <!-- If we need scrollbar -->
                    <div class="swiper-scrollbar"></div>
                </div>

            </div>
        </section>
</template>

<style scoped></style>
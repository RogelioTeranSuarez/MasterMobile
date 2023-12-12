<template>
    <Navbar />
    <Banner />
    <Popular />
    <Cookie />
    <FooterComponent />
</template>

<script>
import Navbar from '../components/navbar.vue'
import Banner from '../components/banner.vue'
import FooterComponent from '../components/footer.vue'
import Popular from '../components/popular.vue'
import Cookie from '../components/cookie.vue'

export default {
    components: {
        Navbar,
        Banner,
        FooterComponent,
        Popular,
        Cookie
    },
}
</script>

<style></style>
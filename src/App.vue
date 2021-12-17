<template>
    <div class="container">
        <Navbar />
        <router-view />
        <Footer />
    </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import Footer from "@/components/Footer.vue";
export default {
    name: "App",
    components: {
        Navbar,
        Footer,
    },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,300;0,400;0,500;0,600;0,700;1,300;1,400;1,500;1,600;1,700&display=swap");
* {
    font-family: "Poppins", sans-serif;
    color: #808b97;
}
a {
    text-decoration: none;
}
a:hover {
    text-decoration: underline;
}
::selection {
    background: #fff1c1;
}
.container {
    max-width: 42rem;
    padding: 120px 60px;
    margin-left: auto;
    margin-right: auto;
}
@media screen and (max-width: 700px) {
    .container {
        padding: 30px;
    }
}
</style>

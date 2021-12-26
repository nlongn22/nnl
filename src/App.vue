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
:root {
    --background-color: #fbfbfb;
    --foreground-color: #808b97;
    --accent-color: #78b7bb;
    --selection-color: #fff1c1;
}
:root.dark-theme {
    --background-color: #232931;
    --foreground-color: #eeeeee;
    --accent-color: #4ecca3;
    --selection-color: #393e46;
}
::-webkit-scrollbar {
    width: 10px;
}
::-webkit-scrollbar-track {
    background: var(--background-color);
}
::-webkit-scrollbar-thumb {
    border-radius: 5px;
    background: var(--foreground-color);
}
::-webkit-scrollbar-thumb:hover {
    background: var(--accent-color);
}
::selection {
    background: var(--selection-color);
}
body {
    background-color: var(--background-color);
    transition: 0.5s;
}
* {
    font-family: "Poppins", sans-serif;
    color: var(--foreground-color);
}
a {
    text-decoration: none;
}
a:hover {
    text-decoration: underline;
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

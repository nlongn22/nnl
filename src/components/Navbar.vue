<template>
    <div class="navbar">
        <span id="index" v-bind:class="{ active: this.$route.name === 'Home' }"
            ><router-link v-bind:to="{ name: 'Home' }">Home</router-link></span
        >
        <div class="wrapper">
            <span
                id="blog"
                v-bind:class="{ active: this.$route.name === 'Blog' }"
                ><router-link v-bind:to="{ name: 'Blog' }"
                    >Blog</router-link
                ></span
            >
            <span
                id="projects"
                v-bind:class="{ active: this.$route.name === 'Projects' }"
                ><router-link v-bind:to="{ name: 'Projects' }"
                    >Projects</router-link
                ></span
            >
        </div>
    </div>
</template>

<script>
export default {
    name: "Navbar",
};
</script>

<style scoped>
* {
    color: #78b7bb;
}
.navbar {
    display: flex;
    margin-bottom: 60px;
}
#index {
    margin-right: 30px;
}
.wrapper {
    display: flex;
    column-gap: 15px;
}
#index.active,
#blog.active,
#projects.active {
    font-weight: 500;
}
@media screen and (max-width: 700px) {
    .navbar {
        justify-content: space-between;
    }
}
</style>

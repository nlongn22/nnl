<template>
    <div class="navbar">
        <span
            class="icon"
            v-bind:class="{ active: this.$route.name === 'Home' }"
            ><router-link v-bind:to="{ name: 'Home' }">Home</router-link></span
        >
        <div class="wrapper">
            <span
                class="icon"
                v-bind:class="{ active: this.$route.name === 'Blog' }"
                ><router-link v-bind:to="{ name: 'Blog' }"
                    >Blog</router-link
                ></span
            >
            <span
                class="icon"
                v-bind:class="{ active: this.$route.name === 'Projects' }"
                ><router-link v-bind:to="{ name: 'Projects' }"
                    >Projects</router-link
                ></span
            >
            <i
                id="moon"
                v-bind:class="{
                    'far fa-moon': currentTheme === 'dark-theme',
                    'fas fa-moon': currentTheme === 'light-theme',
                }"
                v-on:click="toggleTheme()"
            ></i>
        </div>
    </div>
</template>

<script>
export default {
    name: "Navbar",
    data() {
        return {
            currentTheme: "",
        };
    },
    methods: {
        getMediaPreference() {
            let prefersDark = window.matchMedia(
                "(prefers-color-scheme: dark)"
            ).matches;
            if (prefersDark) {
                return "dark-theme";
            } else {
                return "light-theme";
            }
        },
        toggleTheme() {
            let currentTheme = localStorage.getItem("current-theme");
            if (currentTheme === "light-theme") {
                this.setTheme("dark-theme");
            } else {
                this.setTheme("light-theme");
            }
        },
        setTheme(theme) {
            this.currentTheme = theme;
            localStorage.setItem("current-theme", theme);
            document.documentElement.className = theme;
        },
    },
    mounted() {
        this.setTheme(this.getMediaPreference());
        window
            .matchMedia("(prefers-color-scheme: dark)")
            .addEventListener("change", (e) => {
                if (e.matches) {
                    this.setTheme("dark-theme");
                } else {
                    this.setTheme("light-theme");
                }
            });
    },
};
</script>

<style scoped>
* {
    color: var(--accent-color);
}
.navbar {
    display: flex;
    justify-content: space-between;
    margin-bottom: 60px;
}
.wrapper {
    display: flex;
    align-items: center;
    column-gap: 15px;
}
.icon.active {
    font-weight: 500;
}
#moon {
    color: var(--foreground-color);
    background-color: var(--backgorund-color);
    transition: 0.3s;
}
#moon:hover {
    cursor: pointer;
    opacity: 0.7;
    transition: 0.3s;
}
@media screen and (max-width: 700px) {
    .navbar {
        justify-content: space-between;
    }
}
</style>

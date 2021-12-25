<template>
    <div class="footer">
        <a
            href="https://www.instagram.com/22longino/"
            class="icon"
            title="Go to instagram.com"
            target="_blank"
        >
            <i class="fab fa-instagram"></i>
        </a>
        <a
            href="mailto:22nlongn@gmail.com"
            class="icon"
            id="email"
            title="Email 22nlongn@gmail.com"
            target="_blank"
        >
            <i class="far fa-envelope"></i>
        </a>

        <a
            href="https://github.com/longino22"
            class="icon"
            title="Go to github.com"
            target="_blank"
        >
            <i class="fab fa-github"></i>
        </a>
    </div>
</template>

<script>
export default {
    name: "Footer",
};
</script>

<style scoped>
.footer {
    margin-top: 60px;
}
.icon {
    transition: 0.3s;
    font-size: 24px;
}
.icon:hover {
    opacity: 0.7;
    transition: 0.3s;
}
#email {
    margin: 0px 15px;
}
</style>

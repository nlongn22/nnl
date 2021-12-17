<template>
    <div class="footer">
        <a
            href="https://www.instagram.com/22longino/"
            class="icon"
            title="Go to instagram.com"
            target="_blank"
        >
            <instagram-icon size="1.5x"></instagram-icon>
        </a>
        <a
            href="mailto:22nlongn@gmail.com"
            class="icon"
            id="email"
            title="Email 22nlongn@gmail.com"
            target="_blank"
        >
            <mail-icon size="1.5x"></mail-icon>
        </a>

        <a
            href="https://github.com/longino22"
            class="icon"
            title="Go to github.com"
            target="_blank"
        >
            <github-icon size="1.5x"></github-icon>
        </a>
    </div>
</template>

<script>
import {
    InstagramIcon,
    MailIcon,
    GithubIcon,
} from "@zhuowenli/vue-feather-icons";

export default {
    name: "Footer",
    components: {
        InstagramIcon,
        MailIcon,
        GithubIcon,
    },
};
</script>

<style scoped>
.footer {
    margin-top: 60px;
}
.icon {
    transition: 0.3s;
}
.icon:hover {
    opacity: 0.7;
    transition: 0.3s;
}
#email {
    margin: 0px 15px;
}
</style>

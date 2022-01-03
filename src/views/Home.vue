<template>
    <div class="brand">
        <span id="name">Nguyen Ngoc Long</span>
        &#8226;
        <span id="job">Web developer</span>
    </div>
    <div class="header">
        {{ message
        }}<span
            class="cursor"
            v-bind:class="{
                blinking: message === 'Enjoy your stay.',
            }"
            >|</span
        >
    </div>
    <div class="description">
        Hey there &#128075;!
        <br />
        My name is Nguyen Ngoc Long but most of my friends call me Filip. I'm a
        full stack web developer who currently lives in Munich, Germany. I am 20
        years old and after high school I've decided to take a gap year before
        entering university to learn German. After finishing high school this
        summer, I decided to start learning the basics of web development.
        <br />
        <br />
        In my free time (when I'm not learning anything) I like to watch TV
        shows or hang out with my friends. I'm quite a big fan of Formula 1 so
        every weekend is spent watching races and following news around this
        great sport. To stay in shape, I try to run at least three times a week
        to stay healthy and clear my head.
    </div>
</template>

<script>
export default {
    name: "Home",
    data() {
        return {
            message: "",
            index: 0,
        };
    },
    methods: {
        typeWriter(string) {
            let stringArray = string.split("");
            this.message += stringArray[this.index];
            this.index++;
        },
        initTypeWriter(string) {
            return new Promise((resolve, reject) => {
                setTimeout(() => {
                    let interval = setInterval(() => {
                        this.typeWriter(string);
                        if (this.message === "Enjoy your stay.") {
                            resolve();
                            clearInterval(interval);
                            return;
                        }
                        if (this.message === string) {
                            this.message = "";
                            this.index = 0;
                            resolve();
                            clearInterval(interval);
                        }
                    }, 150);
                }, 300);
            });
        },
        chainPromises() {
            this.initTypeWriter("Welcome!").then(() =>
                this.initTypeWriter("Enjoy your stay.!")
            );
        },
        setTitle() {
            document.title = "Nguyen Ngoc Long | Home";
        },
    },
    mounted() {
        this.chainPromises();
        this.setTitle();
    },
};
</script>

<style scoped>
.brand {
    margin-bottom: 30px;
}
#name {
    font-weight: 600;
}
#job {
    font-weight: 300;
}
.header {
    margin-bottom: 15px;
    font-size: 48px;
    font-weight: 700;
}
@media screen and (max-width: 700px) {
    .header {
        font-size: 36px;
    }
}
@keyframes blink {
    0% {
        opacity: 0;
    }
}
.cursor {
    font-weight: 400;
    color: var(--accent-color);
}
.cursor.blinking {
    animation: blink 1s steps(2) infinite;
}
</style>

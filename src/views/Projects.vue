<template>
    <div class="projects">
        <div class="project">
            <span
                ><a
                    href="https://mechmarket.eu"
                    title="Go to mechmarket.eu"
                    target="_blank"
                    >MechMarket.eu</a
                >
                <li>Full-stack marketplace for mechanical keyboards</li>
                <li>CRUD operations (Create, Read, Update and Delete posts)</li>
                <li>Authentication (register and login)</li>
                <li>AWS S3 for uploading and deleting images of keyboards</li>
                <li>Communication between server and client via REST API</li>
                <li>Review sellers, filter by category, search by keywords</li>
            </span>
            <span class="tech">
                <i class="fab fa-python"></i>
                <i class="fab fa-vuejs"></i>
                <i class="fab fa-css3-alt"></i>
            </span>
        </div>
        <div class="project">
            <span
                ><a
                    href="https://weather-wizard.xyz"
                    title="Go to weather-wizard.xyz"
                    target="_blank"
                    >Weather-Wizard.xyz</a
                >
                <li>Beautiful weather dashboard</li>
                <li>
                    Predictive searching of any location via Google Maps API
                </li>
                <li>
                    At glance conditions such as humidity, wind speed, UV index,
                    sunrise & sunset, pressure
                </li>
                <li>Filter by weekly or hourly conditions</li>
            </span>
            <span class="tech">
                <i class="fab fa-vuejs"></i>
                <i class="fab fa-css3-alt"></i>
            </span>
        </div>
        <div class="project">
            <span>
                <a
                    href="https://journald.herokuapp.com"
                    title="Go to journald.herokuapp.com"
                    target="_blank"
                    >JournalD</a
                >
                <li>Simple journal app</li>
                <li>CRUD operations</li>
            </span>
            <span class="tech">
                <i class="fab fa-python"></i>
                <i class="fab fa-bootstrap"></i>
                <i class="fab fa-css3-alt"></i>
            </span>
        </div>
        <div class="project">
            <span>
                <a
                    href="https://github.com/longino22/type-4-me"
                    title="Go to github.com"
                    target="_blank"
                    >type-4-me</a
                >
                <li>Auto typing bot with GUI</li>
                <li>Select an area of screen to recognize text</li>
            </span>
            <span class="tech">
                <i class="fab fa-python"></i>
            </span>
        </div>
    </div>
</template>

<script>
export default {
    name: "Projects",
    methods: {
        setTitle() {
            document.title = "Nguyen Ngoc Long | Projects";
        },
    },
    mounted() {
        this.setTitle();
    },
};
</script>

<style scoped>
a {
    color: #78b7bb;
}
.projects {
    display: flex;
    flex-direction: column;
    row-gap: 30px;
}
.project {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
}
li {
    padding-left: 15px;
}
.tech {
    display: flex;
    column-gap: 10px;
}
</style>

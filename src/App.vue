<template>
<div id="app">
    <Banner/>
    <ProjectList v-bind:projects="projects"/>
</div>
</template>

<script>
import Banner from "./components/Banner.vue"
import ProjectList from "./components/ProjectList.vue"
//import axios from "axios";

export default {
    name: "App",
    components: {
        Banner,
        ProjectList
    },
    data() {
        return {
            projects: [
                {
                    id: 1,
                    title: "illumination",
                    description: "physics simulation",
                    languages: ["Java"]
                },
                {
                    id: 2,
                    title: "quicklib",
                    description: "reservation system",
                    languages: ["Javascript", "React"]
                }
            ]
        }
    }
    // created() {
    //     axios.get("https://jsonplaceholder.typicode.com/comments?_limit=5")
    //     .then(res => this.projects = res.data)
    //     .catch(err => console.log(err));
    // }
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>

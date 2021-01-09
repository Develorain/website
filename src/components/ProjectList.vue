<template>
<div>
    <p>Projects</p>
    <Filter/>
    <div v-bind:key="project.id" v-for="project in projects">
        <Project v-bind:project="project"/>
    </div>
</div>
</template>

<script>
import Project from "./Project.vue"
import Filter from "./Filter.vue"

export default {
    name: "ProjectList",
    components: {
        Filter,
        Project
    },
    props: ["projects"]
}
</script>

<style scoped>

</style>
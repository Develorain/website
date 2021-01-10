<template>
<div>
    <p>Projects</p>
    <input type="checkbox" id="java" value="Java" v-model="checkedLanguages">
    <label for="java">Java</label>
    <input type="checkbox" id="javascript" value="Javascript" v-model="checkedLanguages">
    <label for="javascript">Javascript</label>
    <input type="checkbox" id="reactjs" value="ReactJS" v-model="checkedLanguages">
    <label for="reactjs">ReactJS</label>
    <input type="checkbox" id="f#" value="F#" v-model="checkedLanguages">
    <label for="f#">F#</label>
    <input type="checkbox" id="python" value="Python" v-model="checkedLanguages">
    <label for="python">Python</label>
    <input type="checkbox" id="vuejs" value="VueJS" v-model="checkedLanguages">
    <label for="vuejs">VueJS</label>
    <input type="checkbox" id="nodejs" value="NodeJS" v-model="checkedLanguages">
    <label for="nodejs">NodeJS</label>
    <input type="checkbox" id="bootstrap" value="Bootstrap" v-model="checkedLanguages">
    <label for="bootstrap">Bootstrap</label>
    <input type="checkbox" id="angular" value="Angular" v-model="checkedLanguages">
    <label for="angular">Angular</label>
    <input type="checkbox" id="postgresql" value="PostgreSQL" v-model="checkedLanguages">
    <label for="postgresql">PostgreSQL</label>
    <input type="checkbox" id="swing" value="Swing" v-model="checkedLanguages">
    <label for="swing">Swing</label>

    <div v-bind:key="project.id" v-for="project in filteredProjects">
        <Project v-bind:project="project"/>
    </div>
</div>
</template>

<script>
import Project from "./Project.vue"

export default {
    name: "ProjectList",
    components: {
        // ProjectFilter,
        Project
    },
    data() {
        return {
            checkedLanguages: []
        }
    },
    props: ["projects"],
    computed: {
        filteredProjects() {
            const filteredProjects2 = this.projects.filter(proj => {
                var filteredLanguages = proj.languages.filter(lang => this.checkedLanguages.includes(lang));

                if (!Array.isArray(filteredLanguages) || !filteredLanguages.length) {
                    // array does not exist, is not an array, or is empty
                    return false;
                } else {
                    return true;
                }
            });

            return filteredProjects2;
        }
    }
}
</script>

<style scoped>
</style>
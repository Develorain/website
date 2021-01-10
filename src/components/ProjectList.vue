<template>
<div>
    <!-- <ProjectFilter/> -->
    <p>Projects</p>
    <input type="checkbox" id="java" value="Java" v-model="checkedLanguages">
    <label for="java">Java</label>
    <input type="checkbox" id="javascript" value="Javascript" v-model="checkedLanguages">
    <label for="javascript">Javascript</label>
    <input type="checkbox" id="react" value="React" v-model="checkedLanguages">
    <label for="react">React</label>

    <br>
    <span>Checked languages: {{checkedLanguages}}</span>

    <!-- <div v-bind:key="project.id" v-for="project in filteredProjects">
        <p>POG: {{project.title}}</p>
    </div> -->
    <!-- <div>
        Filtered projects language: {{this.filteredProjects}}
    </div> -->

    <div v-bind:key="project.id" v-for="project in filteredProjects">
        <!-- <div v-if="project.language.indexOf(checkedLanguages) !== -1"> -->
            <Project v-bind:project="project"/>
        <!-- </div> -->
    </div>
</div>
</template>

<script>
import Project from "./Project.vue"
// import ProjectFilter from "./ProjectFilter.vue"

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
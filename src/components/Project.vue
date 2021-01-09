<template>
    <p>
        {{project.title}}<br>
        {{project.description}}<br>
        {{project.language}}
    </p>
</template>

<script>
export default {
    name: "Project",
    props: ["project"]
}
</script>

<style scoped>

</style>
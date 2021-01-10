<template>
<div>
    <p>
        {{project.title}}<br>
        {{project.description}}<br>
        {{project.languages}}
    </p>
</div>
</template>

<script>
export default {
    name: "Project",
    props: ["project"]
}
</script>

<style scoped>

</style>
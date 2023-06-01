<script>
export default {
    name: 'ProjectItem',
    
    data() {
        return {

        }
    },

    props:{
        project: Object,
    },

    computed: {
        description() {
            return
        }
    }
}
</script>

<template>
    <div>
        {{project.title}}
    </div>

    <p>
        {{project.description}}
    </p>
</template>
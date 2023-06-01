<script>
import axios from 'axios';

import ProjectItem from './ProjectItem.vue';

export default {
    name: 'AppMain',

    data() {
     return {
        projects: []
     }
     
    },

    components: {
        ProjectItem,
    },

    mounted() {
        this.getProjects();
    },

    methods: {
        getProjects(){
            axios.get('http://127.0.0.1:8000/api/projects').then(response => {
                console.log(response.data.results);
                this.projects = response.data.results;
            })
        },
    }
}
</script>

<template>
    <div class="container">
        <h1>Boolfolio</h1>

        <div class="row">
            <div v-for="project in projects" class="col-4">
                <ProjectItem :project="project"></ProjectItem>
            </div>
        </div>
    </div>
</template>

<style>

</style>
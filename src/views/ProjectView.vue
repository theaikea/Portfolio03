<script>
import projectsData from '@/data/projects.json'

export default {
    data() {
        return {
            project: projectsData.find(project => project.id === this.$route.params.slug)
        }
    }
}

</script>


<template>
    <div class="grid grid-cols-2 mt-20 ml-6">
      <p class="poppins text-7xl text-[#DC4E36] font-bold italic"> {{ project.titleText }} </p>
      <p class="col-start-1 row-start-2 poppins text-2xl mt-10"> {{ project.descriptionText }} </p>
      <img v-if="project.titleImage" class="col-start-1 row-start-3 mt-10" :src="project.titleImage" alt="">
      <video v-else :src="project.video" class="col-start-1 row-start-3 sticky" autoplay muted loop></video>
    </div>
  </template>
  
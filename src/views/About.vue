<template>
  <div class="about">
    <h1>This is an about page</h1>
    <ol>
      <li>Test</li>
      <li v-for="project in projects" v-bind:key="project.id">
        {{ project.id }}
      </li>
    </ol>
  </div>
</template>

<script>
import { db } from '../components/db'

export default {
  data() {
    return {
      projects: [],
    }
  },
  firestore: {
    projects: db.collection('projects'),
  },
}
</script>
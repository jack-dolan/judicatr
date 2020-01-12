<template>
  <div class="about">
    <h1>This is an about page</h1>
    <ol>
      <li>Test</li>
      
    </ol>
  </div>
</template>

<script lang="ts">
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
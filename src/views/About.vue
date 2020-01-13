<template>
  <div class="about">
    <h1>This is an about page</h1>
    <ol>
      <li>Test</li>
      <li v-for="project in projects" v-bind:key="project.id">
        {{ project.id }}
      </li>
    </ol>
    <input id="fileUpload" type="file" hidden @change="fileInput()">
    <button @click="chooseFiles()">Upload CRM</button>
    <p id="fileNameLabel">No file selected</p>
  </div>
</template>

<script>
import { db } from '../components/db'

export default {
  data() {
    return {
      projects: [],
      files: [],
    }
  },
  firestore: {
    projects: db.collection('projects'),
  },
  methods: {
    chooseFiles() {
      document.getElementById("fileUpload").click();
    },
    fileInput() {
      if (document.getElementById("fileUpload").files.length > 0) {
        const myFiles = document.getElementById("fileUpload").files;
        document.getElementById("fileNameLabel").textContent = myFiles[0].name;
      }
    },
  },
}

</script>
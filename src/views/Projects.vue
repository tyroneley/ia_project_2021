<template>
  <div class="header">
    <Header title= "Projects"/>

  </div>

  <div id="app" class="projects">
        <div style="text-align: center;">
            <h3>To do list</h3>
            <br>
        </div>

        <!-- Table of tasks -->
        <table class="table">
            <thead> 
                <tr>
                    <th>Title</th>
                    <th>Content</th>
                    <th></th>
                </tr>
            </thead>

            <tbody>
                <tr v-for="project in projects" :key="project.id">
                    <td>
                        {{ project.title }}
                    </td>
                    <td>
                        {{ project.task }}
                    </td>
                </tr>
            </tbody>

        </table>
    </div>  
</template>

<script type="module">
import Vue from 'vue';
import Header from "../components/Header.vue"
import firebase from "../database/firebaseInit.js"
const db = firebase.firestore();

const App = {
  data() {
      return {
        projects: [],
        title: "",
        content: "",
      }
    },

    mounted() {
      db.collection("projects")
      .get()
      .then((querySnapshot) => {
        querySnapshot.forEach((doc) => {
          this.projects.push({
            title: doc.title,
            content: doc.content
          });
        });
      });
    },

    methods: {
      createProject() {
        db.collection("projects")
          .add({ 
            title: this.title, 
            content: this.content 
            })
      }
    },
}
Vue.createApp(App).mount('#app')

export default {
  name: 'Projects',
  components: {
    Header
  }
}
</script>

<script>
import { axios } from "Vue";

export default {
  data() {
    return{
      count: 0,
      id:0,
      message: 'I am currently learning Vue 3',
      staffs: [
        {id: id++, name: 'Engr. Aniebete', gender: 'male', role: 'Director',complexion: 'fair',},
        {id: id++, name: 'Engr. Lawrence', gender: 'male', role: 'Managing Director',complexion: 'dark',},
        {id: id++, name: 'Mrs. Imaobong', gender: 'female', role: 'Admin',complexion: 'fair',},
        {id: id++, name: 'Mr. Ogo', gender: 'male', role: 'Trainer',complexion: 'fair',},
        {id: id++, name: 'Mr.Joshua', gender: 'male', role: 'Trainer',complexion: 'dark',},
        {id: id++, name: 'Ms.Favour', gender: 'female', role: 'Trainer',complexion: 'dark',},
        {id: id++, name: 'Mr.Kingsley', gender: 'male', role: 'Trainer',complexion: 'dark',},
      ]
    }
  },

  methods: {
    increment() {
      this.count++;
    }
  },

  mounted() {
    axios: {
      get('https://restcountries.com/'),
      then( response => {response.countries.img})
    }
  },
}
</script>

<template>
  <div>
    <button class="btn btn-primary" @click="increment">Increment</button>
    <p>count is {{count}}</p>
    <p>Hey there, {{message.split('').reverse()}}</p>

    <div class="card-section" v-for="staff in staffs" :key="staff.id">
      <div class="card">
        <div class="card-body">
          <p>Name: {{staff.name}}</p>
          <p>Gender: {{staff.gender}}</p>
          <p>Role: {{staff.role}}</p>
          <p>Complexion: {{staff.complexion}}</p>
        </div>
      </div>
    </div>

    <div v-for="country in countries" :key='country.name'>
      {{countries.img}}
    </div>
  </div>

</template>

<style scoped>

</style>

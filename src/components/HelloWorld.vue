<script>
import SousComposant from './SousComposant.vue'
import actionButton from './actionButton.vue'
import subForm from './subForm.vue'

export default {
  name: 'HelloWorld',
  components : {
    SousComposant,
    actionButton,
    subForm
  },
  props: {
    msg: {
      type: [String,Number],
      required: true,
      default: function() {
        return "Bonjour !"
      }
    },
    visibility : {
      type: Boolean,
      required: true,
      default: function() {
        return true
      }
    }
  },
  data() {
    return {
      username: null,
      password: null,
      alert: null,
      people: [
        {
          name: 'Tim',
          age: '28'
        },
        { name: 'Jojo',
          age: '71'
        }
      ]
    }
  },
  methods : {
    testUsername() {
      if(this.username == "john") {
        this.alert = "Hello JOHN WICK"
      } else {
        this.alert = null
      }
    },
    addPerson() {
      this.people.push({ name: 'Pilou', age: '32'})      
    }
  },
  computed : {
    computeTestUsername() {
      if(this.username == "chuck") {
        return true
      } else {
        return false
      }
    }
  }
}
</script>


<template>
  <div class="greetings">
    <h1 
      class="green"
      v-if="visibility === true"
    >
      {{ msg }}
    </h1>
  </div>

  <section>
    <sub-form :inputs="[{ type:'text',name:'Prénom'}, { type:'text',name:'Nom'}, {type:'email',name:'Email'}, {type:'submit', name:'Valider'}]"/> 
    <action-button msg="Ajouter une personne" @click="addPerson" />
  </section>

  <section>
    <ul>
      <li v-for="person in people">{{ person.name }}, {{ person.age }} ans</li>
    </ul>
  </section>

</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

.user-form {
  margin-top: 10px;
  display: flex;
}

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>

<template>  
  <client-only>
  <nav class="uk-navbar-container" uk-navbar>
      <div class="uk-navbar-left">

          <ul class="uk-navbar-nav">
              <li class="uk-active"><router-link tag="a" class="navbar-brand" to="/" exact>Deliveroo clone</router-link></li>
              <li><router-link tag="a" class="navbar-brand" to="/restaurants" exact>Restaurants</router-link></li>
          </ul>

      </div>

      <div class="uk-navbar-right">

          <ul class="uk-navbar-nav" v-if="username">
              <li>
                <a href="#" class="uk-link-reset">
                <img src="https://png2.cleanpng.com/sh/a7adacc7226d2dc438dafb37913a8ab8/L0KzQYm3V8E2N5tqipH0aYP2gLBuTfVudZZ5ReZxZT3vdbj2Tf1wfppqRehyZHXyd7L0hb1xeppze9d8cz34frryigR1gV58Rdd2bXX3Pb3shB8udZD7gdc2NXK3coG9UMRibGJrfqI3Mkm0RoS7VMYyPWQ2TqY8M0m5R4GCUb5xdpg=/kisspng-emmet-the-lego-movie-videogame-princess-unikitty-w-emmet-lego-movie-5b4b0604ad1ff0.2916344615316433967091.png" 
                class="uk-border-circle" 
                height="40" 
                width="40" 
                alt="">{{ username }}</a></li>
              <li><a href="#" @click="logout">Logout</a></li>
          </ul>
          <ul class="uk-navbar-nav" v-else>
              <li><a href="/users/register">Signup</a></li>
              <li><a href="/users/signin">Signin</a></li>
          </ul>

      </div>

  </nav>
</client-only>

</template>

<script>  
import { mapMutations } from 'vuex'

export default {  
  computed: {
    // Set your username thanks to your getter
    username() {
      return this.$store.getters['auth/username']
    }
  },
  methods: {
    // Define your needed mutations, here: auth/logout
    ...mapMutations({
      logout: 'auth/logout'
    })
  }
}
</script>  
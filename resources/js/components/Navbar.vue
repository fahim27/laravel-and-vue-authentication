<template>

<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Logo</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav mr-auto">
      
      <li class="nav-item">
		    <router-link to="/"class="nav-link">Home</router-link>

      </li>
	  <li class="nav-item"v-if="app.user">
		    <router-link to="/welcome"class="nav-link">welcome</router-link>
      </li>
	   <li class="nav-item">
      </li>
	 
	</ul>
	
	
  </div>
  
  <div class="dropdown">
  <button class="btn btn-secondary dropdown-toggle" type="button" id="dropdownMenuButton" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
  {{app.user ?"DashBoard":"Account"}}
  </button>
  <div class="dropdown-menu" aria-labelledby="dropdownMenuButton">
    <a class="dropdown-item" href="#" v-if="app.user" @click="logout">Logout</a>
	<div v-if="!app.user">
	 
	 		    <router-link to="/login"class="dropdown-item">Login</router-link>
	 		    <router-link to="/register"class="dropdown-item">Register</router-link>

	</div>
   
  </div>
</div>
</nav>



</template>

<script>
    export default {
	
		name:"Navbar",
		props: ['app'],
		methods:{
		  logout(){
			axios.post('/logout')
			.then((resp)=>{
				this.app.user=null
				this.$route.push('/login')
			})
			.catch((error)=>{
			  console.log(error)
			})
		  }
		
		
		},
        mounted() {
            console.log('Component mounted.')
        }
    }
</script>
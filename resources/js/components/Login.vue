<template>

<div class="row justify-content-center">
	<div class="col-lg-8 mt-5">
	   <div class="card">
			<div class="card-header">
				<h2 class="text-center">ll</h2>
			</div>
			<div class="card-body">
			
			<div class="alert alert-danger" role="alert" v-if="errors">
			<ul class="mb-0">
							 <li v-for="error in errors">{{error}}</li>

			</ul>
				
		    </div>
					
				  <div class="form-group">
					<label for="exampleInputEmail1">Email address</label>
					<input type="email" class="form-control"  v-model="dataLog.email" aria-describedby="emailHelp" placeholder="Enter email">
				  </div>
				  <div class="form-group">
					<label for="exampleInputPassword1">Password</label>
					<input type="password" class="form-control" v-model="dataLog.password" placeholder="Password">
				  </div>
				  
				  <button @click="login" class="btn btn-primary" style="width:100%;">Submit</button>
			
			</div>
	   </div>
		
	</div>

</div>


</template>

<script>


    export default {
	    name:"Login",
		props: ['app'],
	
		data(){
		 
		  return{
			dataLog:{
			email:"",
			 password:""
			},
			errors:""
				
		  }
		},	
      
		methods:{
		  login(){
		  axios.post('/login',this.$data.dataLog)
		  .then((resp)=>{
		  this.app.user=resp.data;
			this.$route.push("/welcome")
		  })
		  .catch((error)=>{
		   
		   this.errors=error.response.data.errors;
		   
		  
		  })
		  }
		},
		  mounted() {
            console.log('Component mounted.')
        },
		
		
    }
</script>
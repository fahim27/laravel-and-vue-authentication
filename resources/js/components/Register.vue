<template>

<div class="row justify-content-center">
	<div class="col-lg-8 mt-5">
	   <div class="card">
			<div class="card-header">
				<h2 class="text-center">R</h2>
			</div>
			<div class="card-body">
			
			<div class="alert alert-danger" role="alert" v-if="errors">
			<ul class="mb-0">
							 <li v-for="error in errors">{{error}}</li>

			</ul>
				
		    </div>
				
				  <div class="form-group">
					<label>Name</label>
					<input type="text" class="form-control" v-model="dataReg.name"  placeholder="Enter Name">
				  </div>
				  <div class="form-group">
					<label>Email</label>
					<input type="email" class="form-control" v-model="dataReg.email"  placeholder="Email">
				  </div>
				   <div class="form-group">
					<label>Password</label>
					<input type="password" class="form-control" v-model="dataReg.password"  placeholder="password">
				  </div>
				  
				  <button class="btn btn-primary" style="width:100%;" @click="save" >Submit</button>
				
			</div>
	   </div>
		
	</div>
	


</div>


</template>

<script>


    export default {
	    name:"Register",
		props: ['app'],
	
		data(){
		 
		  return{
			dataReg:{
			 name:"",
			 email:"",
			 password:""
			},
			errors:""
				
		  }
		},	
      
		methods:{
		  save(){
		  axios.post('/register',this.$data.dataReg)
		  .then((resp)=>{
		  this.app.user=resp.data;
		  })
		  .catch((error)=>{
		   console.log(this.app)
		   
		   this.errors=error.response.data.errors;
		   console.log()
		  
		  })
		  }
		},
		  mounted() {
            console.log('Component mounted.')
        },
		
		
    }
</script>
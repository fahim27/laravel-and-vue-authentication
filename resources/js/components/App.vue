<template>
<div>

<Navbar :app="this"></Navbar>
<router-view :app="this"></router-view>

</div>


</template>
<script>

import Navbar from "./Navbar.vue";

    export default {
	name:"app",
	components: {
	Navbar
 },
		data(){
			return{
				user:null
			}
		},
        mounted() {
            console.log(this.$data)
        }
    }
</script>
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
	  <li class="nav-item">
		    <router-link to="/welcome"class="nav-link">Welcome</router-link>
      </li>
	   <li class="nav-item">
		    <router-link to="/login"class="nav-link">Login</router-link>
      </li>
	  <li class="nav-item">
		    <router-link to="/register"class="nav-link">Register</router-link>
      </li>
	</ul>
    <form class="form-inline my-2 my-lg-0">
      <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search">
      <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
    </form>
  </div>
</nav>
</template>
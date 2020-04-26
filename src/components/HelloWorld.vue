<template>
  <div class="hello">

  <nav class="navbar navbar-expand-lg sticky-top navbar-light bg-light">
  <a class="navbar-brand text-warning" href="#">
    <img src="imglogo.png" width="30" height="30" class="d-inline-block align-top" alt="">
    MovieInfo
  </a>

  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav mr-auto">
      <li class="nav-item active">
        <a class="nav-link text-info" href="#">Home <span class="sr-only">(current)</span></a>
      </li>
      <li class="nav-item active">
        <a class="nav-link text-info" href="#m">Top Rated <span class="sr-only">(current)</span></a>
      </li><li class="nav-item active">
        <a class="nav-link text-info" href="#m2">Upcoming <span class="sr-only">(current)</span></a>
      </li>
     
      <li class="nav-item active dropdown">
        <a class="nav-link dropdown-toggle text-info" href="#" id="navbarDropdown" role="button" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
          Catagory
        </a>
        <div class="dropdown-menu" aria-labelledby="navbarDropdown">
          <a class="dropdown-item" href="#">Latest</a>
          <a class="dropdown-item" href="#m">Top Rated</a>
          
          <a class="dropdown-item" href="#m2">Upcoming</a>
        </div>
      </li>
     
    </ul>
    <form class="form-inline my-2 my-lg-0">
      <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search" id="ival">
      <button class="btn btn-success my-2 my-sm-0" type="submit" onclick="search()">Search</button>
    </form>
  </div>
</nav>

<div class="container-fluid jumbotron">

<h1 class="text-success">Welcome to MovieInfo</h1><br>

<a href="#m"><button type="button" class="btn btn-primary btn-lg mr-sm-4">Top Rated</button></a>

<a href="#m2"><button type="button" class="btn btn-info btn-lg mr-sm-2">Upcoming</button></a>


<div class="mar" id="m" style="margin-top:-20px;"><br><br><br>

<div class="alert alert-info" role="alert" id="d">

  Top Rated Movies
  
</div>
<br>

<div class="" id="demo"></div>
<div class="" id="demop2"></div>

</div>

<hr>

<div class="mar" id="m2" >
<br><br><br>

<div class="alert alert-info" role="alert" id="d2">

  Upcoming Movies
  
</div>

<br>

<div class="" id="demo2"></div>
<div class="" id="demo2p2"></div>


<br><br><br>
</div>

<div class="jumbotron-fluid">
<hr><br><br>
  <div class="container">
    <h1 class="display-4 text-warning"><img src="imglogo.png" width="80" height="80" class="d-inline-block align-top" alt="Image">MovieInfo</h1>
    <p class="lead text-info">Website to display Top Rated Movies and Upcoming Movies consuming The Movie Database APIs.</p>
  </div>
</div>

</div>

</div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}


let url='https://api.themoviedb.org/3/movie/top_rated?api_key=c7846789a0bcb743f2b3fc48f1fd6bc9&language=en-US&page=1';

var i,x= "";



  fetch(url)
  .then((res)=>res.json())
  .then((data)=>
  {
     console.log('Data' , data);

     for (i=0;i<18;i++) 
     {
 

  x +='<img src="https://image.tmdb.org/t/p/w200/'+ data.results[i].poster_path+'"alt="Jaws"/>' ;

}
document.getElementById("demo").innerHTML = x;
 
  })
  .catch((error)=>
  {
      console.log('Error',error);
  });

  let urlp2='https://api.themoviedb.org/3/movie/top_rated?api_key=c7846789a0bcb743f2b3fc48f1fd6bc9&language=en-US&page=2';

var x2= "";



  fetch(urlp2)
  .then((res)=>res.json())
  .then((data)=>
  {
     console.log('Data' , data);

     for (i=0;i<18;i++) 
     {
 

  x2 +='<img src="https://image.tmdb.org/t/p/w200/'+ data.results[i].poster_path+'"alt="Jaws"/>' ;

}
document.getElementById("demop2").innerHTML = x2;
 
  })
  .catch((error)=>
  {
      console.log('Error',error);
  });




let url2="https://api.themoviedb.org/3/movie/upcoming?api_key=c7846789a0bcb743f2b3fc48f1fd6bc9&language=en-US&page=1";

let y="";

  fetch(url2)
  .then((res)=>res.json())
  .then((data)=>
  {
     console.log('Data' , data);

     for (i=0;i<18;i++) 
     {
 

  y +='<img src="https://image.tmdb.org/t/p/w200/'+ data.results[i].poster_path+'"alt="Jaws"/>' ;

}
document.getElementById("demo2").innerHTML = y;
 
  })
  .catch((error)=>
  {
      console.log('Error',error);
  });

  

let url2p2="https://api.themoviedb.org/3/movie/upcoming?api_key=c7846789a0bcb743f2b3fc48f1fd6bc9&language=en-US&page=2";

let y2="";

  fetch(url2p2)
  .then((res)=>res.json())
  .then((data)=>
  {
     console.log('Data' , data);

     for (i=0;i<18;i++)
     {
 

  y2 +='<img src="https://image.tmdb.org/t/p/w200/'+ data.results[i].poster_path+'"alt="Jaws"/>' ;

}
document.getElementById("demo2p2").innerHTML = y2;
 
  })
  .catch((error)=>
  {
      console.log('Error',error);
  });

</script>



<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.mar
{
 margin:50px;
}


</style>

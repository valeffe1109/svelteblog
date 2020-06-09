<script>
export let segment;
</script>

<style>
nav{
    border-bottom:1px solid rgba(255,62,0,0.1);
    font-weight:300;
    padding:0 1em;
    max-width:56em;
    margin: 0 auto;
}
ul{
    margin:0;
    padding:0;
}
ul:after{
    content:'';
    display:block;
    clear:both;
}
li{
    display:block;
    float:left;
}
.selected{
    position:relative;
    display:inline-block;
}
.selected::after{
    position:absolute;
    content:'';
    width:calc(100%-1em);
    height:2px;
    background-color:rgb(255,62,0);
    display:block;
    bottom:-1px;
}
a{
    text-decoration:none;
    padding:1em 0.5em;
    display:block;
    text-transform:uppercase;
}
</style>

<nav>
  <ul>
    <li><a rel="prefetch"  class='{segment === "home" ? "selected" : ""}' href="home">home</a></li>
    <li><a rel="prefetch"  class='{segment === "about-us" ? "selected" : ""}' href="about-us">about</a></li>
    <li><a rel="prefetch"  class='{segment === "blog" ? "selected" : ""}' href="blog">blog</a></li>
  </ul>

</nav>

<template>
    <div class="mainBox">
        <div id="wrap">
            <nav>
                <ul>
                    <div class="logo">
                        <NuxtLink to="/"><img src = "~/assets/triangle.png"></NuxtLink>
                    </div>
                    <div class="navbar">
                        <li><NuxtLink to="project">My Project</NuxtLink></li>
                        <li><NuxtLink to="contact">Contact</NuxtLink></li>
                    </div>
                </ul>
            </nav>
            <div class = "project">
                <div class = "text">
                    <div v-for="project in res" :key="project.id">
                        {{project.url.split('/').pop()}}
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>

@keyframes fade {
    From {
    Opacity : 0 ;
    }
    To {
    Opacity : 1 ;
    }
}

.mainBox {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 100vw;
    height: 100vh;
}

#wrap {
        width: 100vw;
        height: 50px;
        margin: 0;
        z-index: 99;
        position: fixed;
        top: 0;
        right: 0;
        background-color: gray;
      }
.navbar {
  height: 50px;
  padding: 0;
  margin: 0;
  right: 0;
  position: absolute;
}

.navbar li {
  height: auto;
  width: 135.8px;
  float: left;
  text-align: center;
  list-style: none;
  font: normal bold 13px/1em Arial, Verdana, Helvetica;
  padding: 0;
  margin: 0;
  background-color: gray;
}

.navbar a {
  padding: 18px 0;
  border-left: 1px solid #ccc9c9;
  text-decoration: none;
  color: white;
  display: block;
}
.navbar li:hover {
  background-color: #444444;
}

.navbar li ul {
  display: none;
  height: auto;
  margin: 0;
  padding: 0;
}

.navbar li:hover ul {
  display: block;
}

.navbar li ul li{
  border-left: 1px solid #444444;
  border-right: 1px solid #444444;
  border-top: 1px solid #c9d4d8;
  border-bottom: 1px solid #444444;
}

.project {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100vw;
  height: 100vh;
}

.logo {
    top: -5px;
    left: 0;
    position: fixed;
    width: 4%;
    height: 50px;
    padding: 0;
    margin: 0;
    right: 0;
    position: absolute;
    width: min(50vw, 60px);
}

.text{
    animation-name: fade;
    animation-duration: 4s;
}

</style>

<script setup>
    let res = await $fetch('/api/hello')
    console.log(res)
</script>

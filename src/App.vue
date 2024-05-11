
<template>
  <div>
    <header>
     <h1>map</h1>
    </header>
  
    <main>
      <Map></Map>
    </main>
    <button @click="address">
      click
    </button>
  </div>
</template>

<script setup>
import Map from './components/map.vue'

async function address (){
  const data = await fetch('https://api.neshan.org/v5/reverse?lat=15&lng=12' , {
    method: 'GET',
    headers: {
      'Api-Key': 'service.0a789d697fce4b0697252fe64cb4e4b9'
    }
  })
  console.log(data)
}
</script>

<style scoped>
header {
  line-height: 1.5;
}
main {
  height: 80rem;
  width: 100%;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>

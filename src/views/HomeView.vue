<template>
  <section>
    <h1 class="header">Our Pricing</h1>
    <div class="range">
      <p>Annually</p>
      <button></button>
      <p>Monthly</p>
    </div>

    <div class="container">
      <div class="item">
        <p class="tier">Basic</p>
        <div class="pricing">
        <p class="monthly" v-if="annually === false">19.99</p>
        <p class="annually" v-else-if="annually !== false"></p>
        </div>
        <div>
          <p class="storage">500 GB Storage</p>
          <p class="users">2 Users</p>
          <p class="upload">3GB</p>
        </div>
         <button>LEARN MORE</button>
      </div>
      <div class="item special">
        <p class="tier">Professional</p>
        <div class="pricing">
        <p class="monthly" v-if="annually === false"></p>
        <p class="annually" v-else-if="annually !== false"></p>
        </div>
        <div>
          <p class="storage"></p>
          <p class="users"></p>
          <p class="upload"></p>
        </div>
         <button>LEARN MORE</button>
      </div>
      <div class="item">
        <p class="tier">Master</p>
        <div class="pricing">
        <p class="monthly" v-if="annually === false">24.99</p>
        <p class="annually" v-else-if="annually !== false"></p>
        </div>
        <div>
          <p class="storage"></p>
          <p class="users"></p>
          <p class="upload"></p>
        </div>
         <button>LEARN MORE</button>
      </div>
    </div>
  </section>
</template>

<script>

export default {
  data() {
    return {
      cards: [
        {
          id: 1,
          tier: 'Basic',
          monthly: '19.99',
          annually: '',
          storage: '500GB',
          users: '2',
          upload: '3GB',
        },
        {
          id: 2,
          tier: 'Professional',
          monthly: '24.99',
          annually: ' ',
          storage: '1TB',
          users: '5',
          upload: '10GB',
        },
        {
          id: 3,
          tier: 'Master',
          monthly: '39.99',
          annually: ' ',
          storage: '2TB',
          users: '10',
          upload: '20GB',
        },
      ]
    }
    return {
      annually: false
    }
  }
}
</script>

<style scoped>
section {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100vh;
  background: var(--verylightgreyblue);
  font-family: "Montserrat";
}
.container {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  column-gap: 0;
}
.item {
  width: 25rem;
  height: 25rem;
  box-shadow: 0px 0px 10px 1px rgba(0, 0, 0, 0.144);
}
.item:nth-child(1) {
  border-top-left-radius: 12px;
  border-bottom-left-radius: 12px;
}
.item:nth-child(3) {
  border-top-right-radius: 12px;
  border-bottom-right-radius: 12px;
}
.special {
  height: 35rem;
  background-image: linear-gradient(hsl(236, 72%, 79%), hsl(237, 63%, 64%));

  border-radius: 12px;
}
.price::before{
  content: '$';
}
.users::after{
content: ' Users Allowed'
}
</style>

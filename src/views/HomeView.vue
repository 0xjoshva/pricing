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
          <p class="monthly" v-if="annually = true">19.99</p>
          <p class="annually" v-else-if="annually = false">0</p>
        </div>
        <div>
          <p class="storage">500 GB</p>
          <p class="users">2</p>
          <p class="upload">3GB</p>
        </div>
        <button>LEARN MORE</button>
      </div>
      <div class="item special">
        <p class="tier">Professional</p>
        <div class="pricing">
          <p class="monthly" v-if="annually = true">24.99</p>
          <p class="annually" v-else-if="annually = false"></p>
        </div>
        <div>
          <p class="storage">1 TB</p>
          <p class="users">5</p>
          <p class="upload">10GB</p>
        </div>
        <button>LEARN MORE</button>
      </div>
      <div class="item">
        <p class="tier">Master</p>
        <div class="pricing">
          <p class="monthly" v-if="annually = true">39.99</p>
          <p class="annually" v-else-if="annually = false"></p>
        </div>
        <div>
          <p class="storage">2 TB</p>
          <p class="users">10</p>
          <p class="upload">20GB</p>
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
          tier: "Basic",
          monthly: "19.99",
          annually: "",
          storage: "500GB",
          users: "2",
          upload: "3GB",
        },
        {
          id: 2,
          tier: "Professional",
          monthly: "24.99",
          annually: " ",
          storage: "1TB",
          users: "5",
          upload: "10GB",
        },
        {
          id: 3,
          tier: "Master",
          monthly: "39.99",
          annually: " ",
          storage: "2TB",
          users: "10",
          upload: "20GB",
        },
        
      ],
       annually: false,
    };
   
  },
};
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
  width: 22rem;
  height: 27rem;
  box-shadow: 0px 0px 20px 3px rgba(0, 0, 0, 0.144);
  padding: 2rem;
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
  height: 30rem;
  background-image: linear-gradient(hsl(236, 72%, 79%), hsl(237, 63%, 64%));
  color: var(--verylightgreyblue) !important;
  border-radius: 12px;
  padding: 2rem;
}
.item button {
  width: 100%;
  padding-top: 0.7rem;
  padding-bottom: 0.7rem;
  font-family: "Montserrat";
  font-weight: 700;
  color: white;
  border: none;
  font-size: .8rem;
  border-radius: 6px;
  background: linear-gradient(90deg, hsl(236, 72%, 79%), hsl(237, 63%, 64%));
}
.special button {
  color: hsl(237, 63%, 64%);

  background: var(--verylightgreyblue);
}
.monthly::before,.annually::before {
  content: "$";
  font-size: 2rem;
  vertical-align: middle;
  padding-right: .5rem;

}
.users::after {
  content: " Users Allowed";
}
p{
   width: 100%;
  text-align: center;
  font-size: 1rem;
  font-weight: 600;
  color: var(--darkgreyblue);
}
.special p{
  color: var(--verylightgreyblue);
}
.tier {
  width: 100%;
  text-align: center;
  font-size: 1.2rem;
  font-weight: 600;
  color: var(--darkgreyblue);
  padding-bottom: 1rem;
}
.special .tier {
  color: var(--verylightgreyblue);
  padding-top: 1.5rem;
}
.monthly , .annually{
  font-size: 3.2rem;
  font-weight: 700;
  color: var(--darkgreyblue);
}
.special .monthly,.special .annually{
  color: var(--verylightgreyblue);
}
.special .storage,.special  .users, .special .upload{
    padding: .8rem;
  border-top: 1px solid hsla(240, 80%, 98%, 0.205);
}
.storage, .users, .upload{
    padding: .8rem;
  border-top: 1px solid hsla(234, 14%, 74%, 0.39);
}
.storage{
  margin-top: 1rem;
}
.upload{
  border-bottom: 1px solid hsla(234, 14%, 74%, 0.39);
   margin-bottom: 2rem;
}
.special .upload{
  border-bottom:1px solid hsla(240, 80%, 98%, 0.205);
 
}
.upload::before{
  content: 'Send up to '
}
.storage::after{
content: ' Storage'
}
</style>

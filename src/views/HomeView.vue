<template>
  <section>
    <!-- <img src="../assets/bg-bottom.svg" alt="" class="bottom"> -->
    <h1 class="header">Our Pricing</h1>
    <div class="range">
      <p class="inactive" :class="{ active: monkey }">Monthly</p>

      <label class="switch">
        <input type="checkbox"  />
        <span class="slider round" @click="monkey = !monkey"></span>
      </label>
      <p class="inactive" :class="{ active: !monkey }">Annually</p>
    </div>

    <div class="container">
      <div class="item">
        <p class="tier">Basic</p>
        <div class="pricing">
          <p class="monthly" v-show="monkey === true">19.99</p>
          <p class="annually" v-show="monkey !== true">199.99</p>
        </div>
        <div>
          <p class="storage">500 GB</p>
          <p class="users">2</p>
          <p class="upload">3GB</p>
        </div>
        <button>LEARN MORE</button>
      </div>
      <div class="special item ">
        <p class="tier">Professional</p>
        <div class="pricing">
          <p class="monthly" v-show="monkey === true">24.99</p>
          <p class="annually" v-show="monkey !== true">249.99</p>
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
          <p class="monthly" v-show="monkey === true">39.99</p>
          <p class="annually" v-show="monkey !== true">399.99</p>
        </div>
        <div>
          <p class="storage">2 TB</p>
          <p class="users">10</p>
          <p class="upload">20GB</p>
        </div>
        <button>LEARN MORE</button>
      </div>
    </div>
    <img src="../assets/bg-top.svg" alt="" class="top" />
  </section>
</template>

<script>
export default {
  data() {
    return {
      monkey: true,
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
  min-height: 100vh;
  height: fit-content;
  background: url(../assets/bg-bottom.svg), var(--verylightgreyblue);
  background-repeat: no-repeat;
  background-position: bottom left;
  background-clip: content-box;
  background-size: 30%;
  font-family: "Montserrat";
  z-index: 0;
  position: relative;
}

.container {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  column-gap: 0;
  position: relative;
  z-index: 9999;
}
.item {
  width: 22rem;
  height: 27rem;
  box-shadow: 0px 0px 20px 3px rgba(0, 0, 0, 0.144);
  padding: 2rem;
  position: relative;
  z-index: 3;
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
  font-size: 0.8rem;
  border-radius: 6px;
  background: linear-gradient(90deg, hsl(236, 72%, 79%), hsl(237, 63%, 64%));
  transition: 0.1s ease-in-out all;
}
.special button {
  color: hsl(237, 63%, 64%);

  background: var(--verylightgreyblue);
}
.monthly::before,
.annually::before {
  content: "$";
  font-size: 2rem;
  vertical-align: middle;
  padding-right: 0.5rem;
}
.users::after {
  content: " Users Allowed";
}
p {
  width: 100%;
  text-align: center;
  font-size: 1rem;
  font-weight: 600;
  color: var(--darkgreyblue);
}
.special p {
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
.monthly,
.annually {
  font-size: 3.2rem;
  font-weight: 700;
  color: var(--darkgreyblue);
}
.special .monthly,
.special .annually {
  color: var(--verylightgreyblue);
}
.special .storage,
.special .users,
.special .upload {
  padding: 0.8rem;
  border-top: 1px solid hsla(240, 80%, 98%, 0.205);
}
.storage,
.users,
.upload {
  padding: 0.8rem;
  border-top: 1px solid hsla(234, 14%, 74%, 0.39);
}
.storage {
  margin-top: 1rem;
}
.upload {
  border-bottom: 1px solid hsla(234, 14%, 74%, 0.39);
  margin-bottom: 2rem;
}
.special .upload {
  border-bottom: 1px solid hsla(240, 80%, 98%, 0.205);
}
.upload::before {
  content: "Send up to ";
}
.storage::after {
  content: " Storage";
}

.switch {
  position: relative;
  display: inline-block;
  min-width: 60px;
  min-height: 34px;
}

.switch input {
  opacity: 0;
  width: 0;
  height: 0;
}

.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #ccc;
  -webkit-transition: 0.4s;
  transition: 0.4s all ease-in-out;
}

.slider:before {
  position: absolute;
  content: "";
  height: 26px;
  width: 26px;
  left: 4px;
  bottom: 4px;
  background-color: white;
  -webkit-transition: 0.4s;
  transition: 0.4s;
}

input:checked + .slider {
  background: linear-gradient(180deg, hsl(236, 72%, 79%), hsl(237, 63%, 64%));
}

input:focus + .slider {
  box-shadow: 0 0 1px hsl(237, 63%, 64%);
}

input:checked + .slider:before {
  -webkit-transform: translateX(26px);
  -ms-transform: translateX(26px);
  transform: translateX(26px);
}

/* Rounded sliders */
.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}
.range {
  display: flex;
  width: fit-content;
  height: fit-content;
  align-items: center;
  justify-content: center;
  column-gap: 1.5rem;
  padding: 2rem;
  padding-bottom: 3rem;
  position: relative;
  z-index: 3;
}


.header {
  font-size: 2rem;
  color: var(--greyblue);
  position: relative;
  z-index: 3;
}
.item button:active {
  border: 1px solid hsl(237, 63%, 64%);
  color: hsl(237, 63%, 64%);
  background: transparent;
}
.special button:active {
  border: 1px solid white;
  color: white;
  background: transparent;
}
.top {
  position: absolute;
  z-index: -1;
  object-fit: contain;
  width: 100%;
  height: 100vh;
  object-position: top right;
}
.inactive {
  color: var(--lightgreyblue);
   transition: all .2s ease-in-out;
}
.active{
  color: var(--greyblue);
 transition: all .2s ease-in-out;
}
.monthly, .annually{
   animation: monkeynation .3s cubic-bezier(0.18, 0.89, 0.32, 1.28);
}
img .top{
  display: none;
  position: relative;
  z-index: -1;
}
@keyframes monkeynation{
  0%{
    scale: 0.1;
    opacity: 0;
  }
  100%{
    scale: 1;
     opacity: 1;
  }
}

@media only screen and (max-width: 1200px){
    /*Tablets [601px -> 1200px]*/
}
@media only screen and (max-width: 600px){
	/*Big smartphones [426px -> 600px]*/
      section{
      padding-bottom: 2rem;
      padding-top: 4rem;
      background:none;
    }
    .top{
      display: none;
    }
  .container{
    display: flex;
    flex-direction: column;
    row-gap: 1rem;
  }
  .item{
    border-radius: 12px;
  }
}
@media only screen and (max-width: 425px){
	/*Small smartphones [325px -> 425px]*/
}
</style>

<template>
  <Profile/>
  <Skills/>
  <Experience/>
  <School/>
  <Interests/>
  <Contact/>
</template>

<script>
import Profile from './components/Profile.vue';
import Interests from './components/Interests.vue';
import Skills from './components/Skills.vue';
import Experience from './components/Experience.vue';
import School from './components/School.vue';
import Contact from './components/Contact.vue';

export default {
  name: 'App',
  components: {
    Profile,
    Interests,
    Skills,
    Experience,
    School,
    Contact
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  background-image: url(./assets/pattern.jpg);
  background-repeat: repeat;
  background-size: contain;
}

section {
  display: flex;
  flex-direction: column;
  justify-content: center;
  max-width: 500px;
  margin: 30px;
  padding: 50px;
  border-radius: 10px;
  backdrop-filter: blur(20px);
  box-shadow: 0 0 80px rgba(0, 0, 0, 0.2);
}

section p {
  margin: 5px 0 5px;
}

.profile {
  background-color: rgba(255, 0, 255, 0.3);
  border: 2px solid rgba(255, 0, 255, 0.5);
}

.profile div p:nth-child(2) {
  text-transform: uppercase;
}

.skills {
  background-color: rgba(255, 255, 0, 0.3);
  border: 2px solid rgba(255, 255, 0, 0.5);
}

.experience {
  background-color: rgba(0, 255, 255, 0.3);
  border: 2px solid rgba(0, 255, 255, 0.5);
}

.school {
  background-color: rgba(255, 0, 0, 0.3);
  border: 2px solid rgba(255, 0, 0, 0.5);
}

.interests {
  background-color: rgba(0, 255, 0, 0.3);
  border: 2px solid rgba(0, 255, 0, 0.5);
}

.contact {
  background-color: rgba(0, 0, 255, 0.3);
  border: 2px solid rgba(0, 0, 255, 0.5);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.contact form {
  display: flex;
  flex-direction: column;
  justify-content: center;
  max-width: 500px;
}

.contact form .error {
  color: #f33;
  font-weight: bold;
  font-size: 20px;
}
</style>

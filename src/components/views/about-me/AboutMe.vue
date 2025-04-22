<template>
  <div class="container-aboutMe">
    <div class="wrapper-aboutMe">
      <div class="container-illustration">
        <img src="https://res.cloudinary.com/draxxv99e/image/upload/v1709038012/PORTAFOLIO/portada_s05ebw.png" alt="illustration" />
      </div>
      <div class="container-info">
        <h2 class="title">¡About Me!</h2>
        <hr />
        <p class="info">
          Hello! I'm Estiven Arboleda, a passionate software developer with extensive experience
           in both corporate environments and freelance projects. From my early days at Renault Sofasa,
            where I delved into PLC programming and robotic machinery, to my collaboration at Arriendalo,
             where I contributed to the fullstack development of a web platform from scratch, 
             I've found my true passion in creating innovative technological solutions.
             I thrive on diving into new challenges and learning about the latest technologies.
        </p>
        <p class="info">
          As a freelancer, I've had the opportunity to work on a variety of projects,
  from web applications to enterprise systems, 
  always staying up-to-date with market trends and applying best development practices.
        </p>
        <p class="info">
          With a strong foundation in technologies such as React, Node.js,
 and both relational and non-relational databases,
  I'm constantly seeking to expand my knowledge and skills.
   I firmly believe in the importance of lifelong learning and exploring 
   new technologies to stay relevant in such a dynamic field as software development.

        </p>
        <p class="info">
          If you're looking for a committed and passionate developer
 for your next project, I would love to connect with you and explore
  how I can help bring your technological vision to life!
        </p>
        <div class="container-btns">
          <router-link to="/contact-me">Hire Me!</router-link>
          <router-link to="/cv">Check out my dope CV, buddy!</router-link>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import illustration1 from "../../../assets/illustrations/illustration1.png";

export default {
  setup() {
    return {
      illustration1,
    };
  },
};
</script>

<style lang="sass">
@import './styles/aboutMe.scss'
</style>

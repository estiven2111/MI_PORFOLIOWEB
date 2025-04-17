<template>
  <div class="container-contactMe">
    <div class="container-title">
      <img src="https://res.cloudinary.com/draxxv99e/image/upload/v1709088473/PORTAFOLIO/_e4693232-6d55-4c43-a05b-fdc5667709f3_jdzhst.jpg" alt="Illustration4" />
      <h2 class="title">Contact me</h2>
    </div>
    <div class="container-form">
   
      <div class="container-socials">
        <a href="https://wa.link/5njmcv" target="_blank">
          <img :src="iconWpp" alt="Whatsapp" title="Whatsapp">
        </a>
        <a href="https://mail.google.com/mail/?view=cm&to=estiven.a.martinez@gmail.com" target="_blank">
          <img :src="iconGml" alt="Gmail" title="Gmail">
        </a>
        <a href="https://www.linkedin.com/in/estiven-arboleda-marinez-bb9aa61a4/" target="_blank">
          <img :src="iconLinkedin" alt="linkedin" title="linkedin">
        </a>
        <a href="https://github.com/estiven2111" target="_blank">
          <img :src="iconGitH" alt="Github" title="Github">
        </a>
        <a href="https://discord.com/users/1015738626635747399" target="_blank" rel="noopener noreferrer">
        <img :src="iconDiscord" alt="Discord" title="Discord">
      </a>
      </div>
    </div>
  </div>
</template>

<script>
import illustration4 from '../../../assets/illustrations/illustration4.png'
import iconWpp from '../../../assets/icons/socials/iconWpp.png'
import iconGitH from '../../../assets/icons/socials/iconGitH.png'
import iconLinkedin from '../../../assets/icons/socials/iconLinkedin.png'
import iconGml from '../../../assets/icons/socials/iconGmail.png'
import iconDiscord from "../../../assets/icons/socials/iconDiscord.png"

export default {
  setup() {
    const onSubmit = () => {};
    return {
      illustration4,
      iconWpp,
      iconGml,
      iconGitH,
      iconDiscord,
      iconLinkedin,
      onSubmit,
    };
  },
};
</script>

<style lang="sass">
@import './styles/contactMe.scss'
</style>

<template>
  <footer class="container-footer">
    <div class="footer-content">
      <div class="footer-info">
        <h2>Estiven Arboleda</h2>
        <p>Fullstack Developer</p>
        <p>Ubicación: Medellín, Antioquia</p>
        <p>
          Correo:
          <a href="mailto:estiven.a.martinez@gmail.com">estiven.a.martinez@gmail.com</a>
        </p>
      </div>
      <div class="footer-links">
        <a href="https://github.com/estiven2111" target="_blank">
          <img src="../../../assets/icons/socials/iconGitH.png" alt="GitHub" title="GitHub" />
        </a>
        <a href="https://www.linkedin.com/in/estiven-arboleda-marinez-bb9aa61a4/" target="_blank">
          <img src="../../../assets/icons/socials/iconLinkedin.png" alt="LinkedIn" title="LinkedIn"/>
        </a>
        <a href="https://wa.link/5njmcv" target="_blank">
          <img src="../../../assets/icons/socials/iconWpp.png" alt="WhatsApp" title="WhatsApp"/>
        </a>
        <a href="https://discord.com/users/1015738626635747399" target="_blank" rel="noopener noreferrer">
        <img src="../../../assets/icons/socials/iconDiscord.png" alt="Discord" title="Discord">
      </a>
      </div>
    </div>
  </footer>
</template>

<script>

export default {
  
  name: "Footer",
  setup(props) {
    return {};
  },
};
</script>

<style lang="sass">
@import "./styles/footer.scss"
</style>

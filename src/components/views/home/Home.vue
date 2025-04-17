

<template>
  <div class="container-home">
    <div class="container-greeting">
      <div class="container-illustration">
        <a href="https://www.linkedin.com/in/estiven-arboleda-marinez-bb9aa61a4/" target="_blank">
          <img src="https://res.cloudinary.com/draxxv99e/image/upload/v1708993869/PORTAFOLIO/cv_estiven_a0hijc.jpg" alt="Yo" />
        </a> 
      </div>
      <div class="container-skills">
        <div class="skill" v-for="(area, i) in areaName" :key="i">
          <h2 class="title">{{area}} skills</h2>
          <hr width="100%">
          <div class="container-skill-item">
            <div class="skills-wrapper">
              <div class="skill-row" v-for="(chunk, index) in chunkedLanguages(area)" :key="index">
                <div class="skill-item" v-for="l in chunk">
                  <img width="40" :src="l.img" alt="logo" />
                  <span>{{ l.name }}</span>
                  <!-- <Progress :percentProgress="l.percent" :colorProgress="l.color" /> -->
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import picture from "../../../assets/profile.png";
import Progress from "../../layout/progress-bar/Progress.vue";
import { ref, reactive, computed } from "vue";

export default {
  name: "Home",
  components: {
    Progress,
  },
  setup(props) {

    
    const languages = reactive({
      Frontend: [
       
        {
          name: "ReactJs",
          img:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/a/a7/React-icon.svg/2300px-React-icon.svg.png",
          percent: 75,
          color: "#61DBFB",
        },
        {
          name: "JavaScript",
          img: "https://logospng.org/download/javascript/logo-javascript-icon-1024.png",
          percent: 90,
          color: "#CBB130",
        },
        {
          name: "Bootstrap",
          img: "https://upload.wikimedia.org/wikipedia/commons/thumb/b/b2/Bootstrap_logo.svg/2560px-Bootstrap_logo.svg.png",
          percent: 64,
          color: "#563F7B",
        },
        {
          name: "Tailwindcss",
          img: "https://www.vectorlogo.zone/logos/tailwindcss/tailwindcss-icon.svg",
          percent: 64,
          color: "#563F7B",
        },
        {
          name: "Redux",
          img: "https://raw.githubusercontent.com/devicons/devicon/master/icons/redux/redux-original.svg",
          percent: 64,
          color: "#563F7B",
        },
        {
          name: "R.native",
          img: "https://reactnative.dev/img/header_logo.svg",
          percent: 64,
          color: "#563F7B",
        },
        {
          name: "Android",
          img: "https://raw.githubusercontent.com/devicons/devicon/master/icons/android/android-original-wordmark.svg",
          percent: 64,
          color: "#563F7B",
        },
        {
          name: "Xamarin",
          img: "https://raw.githubusercontent.com/detain/svg-logos/780f25886640cef088af994181646db2f6b1a3f8/svg/xamarin.svg",
          percent: 64,
          color: "#563F7B",
        },
        {
          name: "Angular",
          img: "https://angular.io/assets/images/logos/angular/angular.svg",
          percent: 64,
          color: "#563F7B",
        },
       
         {
          name: "Figma",
          img: "https://www.vectorlogo.zone/logos/figma/figma-icon.svg",
          percent: 64,
          color: "#563F7B",
        },
         {
          name: "HTML5",
          img: "https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg",
          percent: 64,
          color: "#563F7B",
        },
       
        {
          name: "CSS3",
          img: "githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg",
          percent: 70,
          color: "#CA6496",
        },
        {
          name: "PHP",
          img: "https://raw.githubusercontent.com/devicons/devicon/master/icons/php/php-original.svg",
          percent: 64,
          color: "#563F7B",
        },
        {
          name: "VueJs",
          img:
            "https://upload.wikimedia.org/wikipedia/commons/thumb/9/95/Vue.js_Logo_2.svg/2367px-Vue.js_Logo_2.svg.png",
          percent: 88,
          color: "#41B883",
        },
       
      ],
      Backend: [
        {
          name: "NodeJs",
          img:
            "https://raw.githubusercontent.com/devicons/devicon/master/icons/nodejs/nodejs-original-wordmark.svg",
          percent: 68,
          color: "#6DA75D",
        },
        {
          name: "Express",
          img: "https://raw.githubusercontent.com/devicons/devicon/master/icons/express/express-original-wordmark.svg",
          percent: 76,
          color: "#868D94",
        },
        {
          name: "C#",
          img: "https://cdn.cdnlogo.com/logos/c/68/c-sharp-800x800.png",
          percent: 45,
          color: "#9A4993",
        },
        {
          name: "Java",
          img: "https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg",
          percent: 45,
          color: "#9A4993",
        },
        {
          name: "MySQL",
          img: "https://www.freepnglogos.com/uploads/logo-mysql-png/logo-mysql-mysql-logo-png-images-are-download-crazypng-21.png",
          percent: 80,
          color: "#CE8B2C",
        },
        {
          name: "SQL",
          img: "https://user-images.githubusercontent.com/4249331/52232852-e2c4f780-28bd-11e9-835d-1e3cf3e43888.png",
          percent: 55,
          color: "#C03040",
        },
        {
          name: "PostgresSQL",
          img: "https://raw.githubusercontent.com/devicons/devicon/master/icons/postgresql/postgresql-original-wordmark.svg",
          percent: 55,
          color: "#C03040",
        },
        {
          name: "MongoDB",
          img: "https://raw.githubusercontent.com/devicons/devicon/master/icons/mongodb/mongodb-original-wordmark.svg",
          percent: 55,
          color: "#C03040",
        },
        {
          name: "Rest-API",
          img: "https://icon-library.com/images/rest-api-icon/rest-api-icon-8.jpg",
          percent: 80,
          color: "#00935B",
        },
        {
          name: "PHP",
          img: "https://raw.githubusercontent.com/devicons/devicon/master/icons/php/php-original.svg",
          percent: 64,
          color: "#563F7B",
        },
        {
          name: ".NET",
          img: "https://raw.githubusercontent.com/devicons/devicon/master/icons/dot-net/dot-net-original-wordmark.svg",
          percent: 64,
          color: "#563F7B",
        },
        
      ],
      Plus: [
        {
          name: "GitHub",
          img: "https://cdn-icons-png.flaticon.com/512/25/25231.png",
          percent: 90,
          color: "#202124",
        },
        // {
        //   name: "Git",
        //   img: "https://www.vectorlogo.zone/logos/git-scm/git-scm-icon.svg",
        //   percent: 64,
        //   color: "#563F7B",
        // },
        {
          name: "GoogleCloud",
          img: "https://static-00.iconduck.com/assets.00/google-cloud-platform-icon-1024x823-mrdn81d1.png",
          percent: 35,
          color: "#FBBC05",
        },
        {
          name: "Railway",
          img: "https://railway.app/brand/logo-dark.svg",
          percent: 40,
          color: "black",
        },
        {
          name: "Azure",
          img: "https://seeklogo.com/images/M/microsoft-azure-logo-85055C44BE-seeklogo.com.png",
          percent: 30,
          color: "#0089D6",
        },
        {
          name: "Firebase",
          img: "https://www.vectorlogo.zone/logos/firebase/firebase-icon.svg",
          percent: 70,
          color: "#0051CD",
        },
        {
          name: "AWS",
          img: "https://raw.githubusercontent.com/devicons/devicon/master/icons/amazonwebservices/amazonwebservices-original-wordmark.svg",
          percent: 70,
          color: "#0051CD",
        },
        {
          name: "Linux",
          img: "https://raw.githubusercontent.com/devicons/devicon/master/icons/linux/linux-original.svg",
          percent: 70,
          color: "#0051CD",
        },
        {
          name: "Heroku",
          img: "https://www.vectorlogo.zone/logos/heroku/heroku-icon.svg",
          percent: 70,
          color: "#0051CD",
        },
        {
          name: "Canva",
          img: "https://upload.wikimedia.org/wikipedia/commons/thumb/0/08/Canva_icon_2021.svg/2048px-Canva_icon_2021.svg.png",
          percent: 80,
          color: "#5F4DE2",
        },
        {
          name: "Ps",
          img: "https://logodownload.org/wp-content/uploads/2019/10/adobe-photoshop-logo.png",
          percent: 40,
          color: "#001E36",
        },
        {
          name: "Matlab",
          img: "https://upload.wikimedia.org/wikipedia/commons/2/21/Matlab_Logo.png",
          percent: 40,
          color: "#001E36",
        },
        {
          name: "Arduino",
          img: "https://cdn.worldvectorlogo.com/logos/arduino-1.svg",
          percent: 40,
          color: "#001E36",
        },
      ],
    });
    const areaName = computed(() => Object.keys(languages))

const chunkedLanguages = (area) => {
  const chunkSize = 2;
  const chunkedArray = [];
  const areaLanguages = languages[area];
  for (let i = 0; i < areaLanguages.length; i += chunkSize) {
    chunkedArray.push(areaLanguages.slice(i, i + chunkSize));
  }
  return chunkedArray;
};

    return {
      areaName,
      picture,
      languages,
      chunkedLanguages
    };
  },
};
</script>

<style lang="sass">
@import './styles/home.scss'
</style>

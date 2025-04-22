<template>
  <div class="container-webPortfolio">
    <div class="container-title">
      <img :src="illustration3" alt="illustration3" />
      <h2 class="title">Portfolio</h2>
      <div class="nav-projects">
        <button
          :class="{ active: !type_frontend }"
          class="btn-kindOfProject"
          @click="change_type(false)"
        >
          Deploys
        </button>
        <!-- <button
          :class="{ active: !type_frontend }"
          class="btn-kindOfProject"
          @click="change_type(true)"
        >
          Backend
        </button> -->
      </div>
    </div>
    <hr />
    <div class="container-projects">
      <div class="wrapper-projects">
        <div
          class="project"
          v-if="!type_frontend"
          v-for="(project, i) in projects.frontend_projects"
          :key="i"
        >
          <div class="info">
            <h3 class="name">{{ project.name }}</h3>
            <p class="desc">{{ project.description }}</p>
            <div class="wrapper-src">
               <a
                :href="project.url_repository_Backend"
                target="_blank"
                class="btn-go go_repository"
                >Open Repository Back! 🔙</a 
              >
              <a
                :href="project.url_repository_Frontend"
                target="_blank"
                class="btn-go go_repository"
                >Open Repository Front! 💻 </a 
              >
              <a
                :href="project.url_deploy"
                target="_blank"
                class="btn-go go_deploy"
                >Open deploy! 🚀</a
              >
            </div>
          </div>
          <div class="wrapper-illustration">
            <!-- <img :src="project.img" alt="project-img" /> -->
            <a :href="project.img" target="_blank" style="display: block; width: 100%; max-width: 600px; margin: auto; border: none;">
  <iframe 
    :src="project.img" 
    style="width: 100%; height: 400px; border: 1px solid #ccc; border-radius: 10px;" 
    loading="lazy">
  </iframe>
</a>
          </div>
        </div>
        <!-- <div
          class="project"
          v-else-if="!type_frontend"
          v-for="(project, i2) in projects.backend_projects"
          :key="i2"
        >
          <div class="info">
            <h3 class="name">{{ project.name }}</h3>
            <p class="desc">{{ project.description }}</p>
            <div class="wrapper-src">
              <a
                :href="project.url_repository"
                target="_blank"
                class="btn-go go_repository"
                >Open repository! 💻</a
              >
              <a
                :href="project.url_deploy"
                target="_blank"
                class="btn-go go_deploy"
                >Open deploy! 🚀</a
              >
            </div>
          </div>
          <div class="wrapper-illustration">
            <img :src="project.img" alt="project-img" />
          </div>
        </div> -->
      </div>
    </div>
  </div>
</template>

<script>
import { reactive, ref } from "vue";
import illustration3 from "../../../assets/illustrations/illustration3.png";

export default {
  setup() {
    const type_frontend = ref(false);
    const projects = reactive({
      frontend_projects: [
      {
  name: "💼 Sistema Inteligente de Facturación",
  description:
    "I developed an Artificial Intelligence 🤖 solution to automate invoice processing and log working hours by project or client. It uses OCR to analyze images 📸 and PDFs, and Azure GPT-4 to extract key data such as company name, tax ID (NIT), subtotal, taxes, and billed concepts. This information is sent directly to an ERP 💻 for seamless integration with accounting processes, improving operational efficiency. The system also connects with OneDrive ☁️ for secure document storage and features two-factor authentication 🔐 with Microsoft to ensure data protection. Ideal for freelancers, agencies, or companies seeking efficiency, automation, and security in their accounting workflows.",
    url_repository_Backend: "https://github.com/estiven2111/backend_sophimatica",
    url_repository_Frontend: "https://github.com/estiven2111/frontend_sophimatica",
  url_deploy: "https://creame-web.web.app",
  img: "https://res.cloudinary.com/draxxv99e/video/upload/v1745000523/IMAGENES%20WEBS/CREAME/EXPLICACION_APP_SOPHIMATICA_oses9d.mp4",
},
        {
  name: "🗳️ Página Web – Candidato al Concejo de Bello",
  description: "I developed a modern and dynamic website 🌐 for a city council candidate in Bello, designed to communicate their political platform in a friendly and creative way 🤝. It features key sections such as biography 👤, government plan 📜, and contact 📩, along with an interactive games section 🎮 aimed at engaging a younger audience and fostering a stronger connection with the community. The project was built using Vue + Vite ⚡ and styled with Tailwind CSS 🎨. For image and video storage and management, Cloudinary ☁️📸 was used, ensuring fast performance and a smooth experience across all devices 📱💻.",
  url_repository_Backend: "https://github.com/estiven2111/portafolio_alex",
  url_repository_Frontend: "https://github.com/estiven2111/portafolio_alex",
  url_deploy: "https://alexandermenesesconcejal.web.app/",
  img: "https://res.cloudinary.com/draxxv99e/video/upload/v1745006476/IMAGENES%20WEBS/CONCEJALALEX/Alex_Concejal_axtufh.mp4",
},
{
  name: "🏠 Arriéndalo – Plataforma Inmobiliaria",
  description:
    "I developed a web platform 🖥️ for managing property rentals and sales 🏘️, combining an intuitive interface with advanced features. The frontend was built using React + Vite ⚛️⚡ with JavaScript, while the backend was developed with Node.js + Express 🛠️. Secure authentication was implemented using JWT 🔐, and multiple APIs were integrated: WhatsApp API 📲 for direct contact, Wompi 💳 for online payments, and Wasi 🏡 for automatic synchronization of properties and clients. Google Maps 🗺️ was also integrated with custom clusters to efficiently visualize areas. The system supports email sending 📧, real-time property management, and delivers a modern, fast, and secure experience. 🚀",
    url_repository_Backend: "https://github.com/estiven2111/InmobiliariaBack",
    url_repository_Frontend: "https://github.com/estiven2111/Inmobiliaria_frontend",
  url_deploy: "https://inmobiliaria-dfcd7.web.app/",
  img:
    "https://res.cloudinary.com/draxxv99e/video/upload/v1745287262/IMAGENES%20WEBS/INMOBILIARIA/INMOBILIARIA_wtv9mr.mp4",
},
{
  name: "🛡️ DotacionesNW – Página de Seguridad Industrial",
  description:
    "I developed **DotacionesNW**, a website tailored for the company’s CEO to enhance online visibility and attract more potential clients 👥. The site includes key sections such as the company’s **vision** and **mission** 🎯, and allows direct contact through **WhatsApp** 📲 and **email** 📧. Users can browse a **product catalog** 🛠️ focused on **industrial safety**, making it easy to purchase and access detailed information. The design prioritizes an intuitive user experience and highlights products in an attractive way to boost sales and increase brand presence in the market.",
    url_repository_Backend: "https://github.com/estiven2111/DotacionesNW",
    url_repository_Frontend: "https://github.com/estiven2111/DotacionesNW",
  url_deploy: "https://dotacionesnw.com/",
  img: "https://res.cloudinary.com/draxxv99e/video/upload/v1745100660/IMAGENES%20WEBS/DOTACIONESNW/DotacionesNW_sf7oj5.mp4",
},
{
  name: "🎤 UrbanClub – Red Social para Artistas",
  description:
    "I developed UrbanClub, an innovative social platform for artists 🎨🎤, allowing users to create accounts, showcase their talents, and connect with others in their creative field. The platform enables users to organize and promote events 🎟️, as well as monetize 💸 their work. Built with Node.js and Express, it ensures scalability and robust performance. Key features include real-time chat 💬 using WebSockets for seamless communication, secure ticket purchases through PayPal 💳, and event location integration via Google Maps 📍 to display precise directions. This platform provides artists with an effective tool to engage with their audience, build a community, and generate income.",
    url_repository_Backend: "https://github.com/estiven2111/Urbanclub_backend",
    url_repository_Frontend: "https://github.com/estiven2111/URBANCLUB_FRONT",
  url_deploy: "https://urbanclub.vercel.app",
  img: "https://res.cloudinary.com/draxxv99e/video/upload/v1745006389/IMAGENES%20WEBS/URBANCLUB/Urbanclub_vgxtef.mp4",
},
{
  name: "🎮 Tarjetas de Videojuegos - Crea y Explora Tarjetas de Juegos",
  description:
    "Desarrollé **Tarjetas de Videojuegos**, una plataforma donde los usuarios pueden **explorar** y **crear tarjetas** personalizadas de videojuegos 🎮. Los usuarios pueden visualizar tarjetas de juegos existentes, cada una con detalles como el nombre del juego, género, descripción y mucho más. Además, la plataforma permite a los usuarios **crear nuevas tarjetas** para sus videojuegos favoritos o incluso inventar nuevos títulos. Los usuarios pueden organizar las tarjetas a través de **filtros avanzados** 🔍, permitiendo ordenar las tarjetas por categorías, nombre o género. Esta plataforma es ideal tanto para jugadores como para desarrolladores que desean compartir o descubrir más sobre los videojuegos de forma interactiva y ordenada.",
  url_repository_Backend: "https://github.com/estiven2111/VideoGames_backend",
  url_repository_Frontend: "https://github.com/estiven2111/VideoGames_Frontend",
  url_deploy: "https://videogames-navy.vercel.app/",
  img: "https://res.cloudinary.com/draxxv99e/video/upload/v1744998494/IMAGENES%20WEBS/VIDEOGAMES/video_PI_eng2hq.mp4",
},
{
  name: "⚙️ Aplicación de Mantenimiento para PLC Siemens",
  description:
    "I developed a mobile application in **C#** using **Xamarin** for **Android**, aimed at improving the response to industrial equipment failures through efficient connectivity with a **Siemens PLC**. The app connects via a **private WiFi network** 🔒 to ensure secure communication and data protection. Its main purpose is to allow maintenance personnel to receive timely notifications 📲 when equipment such as cranes or transfer systems experience failures, speeding up intervention. Additionally, the interface provides detailed information about possible issues and stores all data in a **database** 🗄️, enabling the generation of **KPIs** 📊 for deeper analysis and root cause identification. This contributes to increased operational efficiency and reduced equipment downtime.",
    url_repository_Backend: "https://github.com/estiven2111/Kaizen_mando_plc_app",
    url_repository_Frontend: "https://github.com/estiven2111/Kaizen_mando_plc_app",
  url_deploy: "https://res.cloudinary.com/draxxv99e/video/upload/v1744856847/IMAGENES%20WEBS/RENAULT%20APP/aplicacion_h7zqcv.mp4",
  img: "https://res.cloudinary.com/draxxv99e/video/upload/v1744856847/IMAGENES%20WEBS/RENAULT%20APP/aplicacion_h7zqcv.mp4",
},
{
  name: "📋 Registro Visual de Usuarios",
  description:
    "I developed a modern application that allows for **user registration** through a form where users can upload data such as **first name**, **last name**, **email address**, and a **profile image** 🧑‍💻📸. The information is efficiently stored in **MongoDB** using the **Mongoose** API, and later displayed in an **interactive table** 🧾 with the option to **filter by upload date and time** ⏰📅. The interface was built with **React**, **Redux**, **Vite**, and **Tailwind CSS** 🌈, ensuring a clean, responsive, and high-performance design. On the backend, I used **Node.js** and **Express** to handle routing, business logic, and database connectivity. This app is ideal for companies looking to maintain an organized, visual record of employees, users, or clients.",
    url_repository_Backend: "https://github.com/estiven2111/backend-loggro",
    url_repository_Frontend: "https://github.com/estiven2111/frontend_loggro",
  url_deploy: "https://estivenarboleda-60c01.web.app/",
  img: "https://res.cloudinary.com/draxxv99e/video/upload/v1745003481/IMAGENES%20WEBS/REGISTRO%20USUARIOS/Registro_usuarios_hiv2bw.mp4",
},
// https://estivenarboleda-60c01.web.app/    URL PRUEBA LOGGRRO FALTA MONTAR ACA 

        // {
        //   name: "",
        //   description: "",
        //   url_repository: "",
        //   url_deploy: "",
        //   img: "",
        // },
      ],
      backend_projects: [
        {
          name: "E Commerce App",
          description:
            "Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsum magni, laboriosam ex dicta saepe architecto nemo modi! Pariatur quae dicta et saepe nesciunt corrupti nihil ullam, sapiente dolore tenetur veniam hic error minus? Odio voluptatibus sed  mollitia ratione, similique facilis officiis eveniet, quisquam doloribus rerum temporibus delectus magnam cumque autem!",
          url_repository: "https://co.pinterest.com/pin/662169951482244622/",
          url_deploy: "https://co.pinterest.com/pin/662169951482244622/",
          img: "https://img.freepik.com/psd-gratis/portada-facebook-marketing-digital-plantilla-banner-web_237398-409.jpg",
        },
      ],
    });

    const change_type = (isFrontend) => {
      if (isFrontend && type_frontend) {
        type_frontend.value = true;
      } else if (!isFrontend && !type_frontend) {
        type_frontend.value = false;
      } else if (isFrontend && !type_frontend) {
        type_frontend.value = true;
      } else if (!isFrontend && type_frontend) {
        type_frontend.value = false;
      }
    };

    return {
      projects,
      type_frontend,
      change_type,
      illustration3,
    };
  },
};
</script>

<style lang="sass">
@import './styles/webPortfolio.scss'
</style>

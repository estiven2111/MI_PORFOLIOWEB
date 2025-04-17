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
              <!-- <a
                :href="project.url_repository"
                target="_blank"
                class="btn-go go_repository"
                >Open repository! 💻</a 
              > -->
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
    "Desarrollé una solución con Inteligencia Artificial 🤖 para automatizar el procesamiento de facturas y registrar horas laborales por proyecto o cliente. Utiliza **OCR** para el análisis de imágenes 📸 y PDFs, y **GPT-4 de Azure** para extraer datos clave como razón social, NIT, subtotal, impuestos y conceptos facturados. Esta información es enviada directamente a un **ERP** 💻 para su integración con los procesos contables, mejorando la eficiencia operativa. Además, el sistema se conecta con **OneDrive** ☁️ para el almacenamiento seguro de documentos y tiene **autenticación de dos factores** 🔐 con Microsoft, asegurando la protección de los datos. Ideal para freelancers, agencias o empresas que buscan eficiencia, automatización y seguridad en sus procesos contables.",
  url_repository: "https://creame-web.web.app",
  url_deploy: "https://creame-web.web.app",
  img: "https://creame-web.web.app",
},
        {
  name: "🗳️ Página Web – Candidato al Concejo de Bello",
  description:
    "Desarrollé una página web moderna y dinámica 🌐 para un candidato al Concejo de Bello, enfocada en comunicar su propuesta política de forma cercana y creativa 🤝. Incluye secciones clave como biografía 👤, plan de gobierno 📜 y contacto 📩, además de una sección interactiva de juegos 🎮 pensada para atraer a un público joven y generar mayor conexión con la comunidad. El proyecto fue construido con Vue + Vite ⚡ y estilizado con Tailwind CSS 🎨. Para el almacenamiento y gestión de imágenes y videos se utilizó Cloudinary ☁️📸, asegurando un rendimiento rápido y una experiencia fluida en todos los dispositivos 📱💻.",
  url_repository: "https://alexandermenesesconcejal.web.app/",
  url_deploy: "https://alexandermenesesconcejal.web.app/",
  img:
    "https://alexandermenesesconcejal.web.app/",
},
{
  name: "🏠 Arriéndalo – Plataforma Inmobiliaria",
  description:
    "Desarrollé una plataforma web 🖥️ para la gestión de alquiler y venta de propiedades 🏘️, combinando una interfaz intuitiva con funcionalidades avanzadas. El frontend fue construido con React + Vite ⚛️⚡ usando JavaScript, mientras que el backend se desarrolló con Node.js + Express 🛠️. Se implementó autenticación segura con JWT 🔐 y se integraron varias APIs: WhatsApp API 📲 para contacto directo, Wompi 💳 para pagos en línea, y Wasi 🏡 para sincronización automática de propiedades y clientes. También se integró Google Maps 🗺️ con clústeres personalizados para visualizar zonas eficientemente. El sistema permite enviar correos 📧, gestionar propiedades en tiempo real y ofrecer una experiencia moderna, rápida y segura. 🚀",
  url_repository: "https://pruearriendalo.web.app/",
  url_deploy: "https://pruearriendalo.web.app/",
  img:
    "https://pruearriendalo.web.app/",
},
{
  name: "🛡️ DotacionesNW – Página de Seguridad Industrial",
  description:
    "Desarrollé **DotacionesNW**, una página web orientada al CEO de la empresa para mejorar la visibilidad online y atraer más clientes potenciales 👥. La página incluye secciones clave como la **visión** y **misión** de la empresa 🎯, además de permitir contacto directo a través de **WhatsApp** 📲 y **correo electrónico** 📧. Los usuarios pueden explorar el **catálogo de productos** 🛠️ especializados en **seguridad industrial**, facilitando la compra y el acceso a la información. El diseño está enfocado en una experiencia intuitiva y en resaltar los productos de manera atractiva para impulsar las ventas y aumentar la presencia de la marca en el mercado.",
  url_repository: "https://dotacionesnw.com/",
  url_deploy: "https://dotacionesnw.com/",
  img: "https://dotacionesnw.com/",
},
{
  name: "🎤 UrbanClub – Red Social para Artistas",
  description:
    "Desarrollé **UrbanClub**, una plataforma social innovadora creada especialmente para artistas 🎨🎤. El objetivo principal es permitir que los usuarios creen su cuenta y se den a conocer por sus habilidades, ya sea como cantantes, pintores o cualquier tipo de artista 👩‍🎨🎶. Además, los usuarios pueden crear **eventos** 🎟️, promocionarlos y **monetizarlos** 💸. La aplicación fue construida con **Node.js** en el backend utilizando **Express**, asegurando un rendimiento robusto y escalabilidad. Cuenta con una función de **chat en tiempo real** 💬 implementada con **WebSockets**, lo que permite una comunicación directa y fluida entre los usuarios. Las entradas a los eventos se pueden pagar de manera fácil y segura a través de **PayPal** 💳, y para facilitar la asistencia, se integra con **Google Maps** 📍 para mostrar la ubicación exacta del evento y cómo llegar hasta él. Esta plataforma busca dar a los artistas una forma efectiva de conectarse con su audiencia, crear una comunidad y generar ingresos.",
  url_repository: "https://urbanclub.vercel.app",
  url_deploy: "https://urbanclub.vercel.app",
  img: "https://urbanclub.vercel.app",
},
{
  name: "🎮 Tarjetas de Videojuegos - Crea y Explora Tarjetas de Juegos",
  description:
    "Desarrollé **Tarjetas de Videojuegos**, una plataforma donde los usuarios pueden **explorar** y **crear tarjetas** personalizadas de videojuegos 🎮. Los usuarios pueden visualizar tarjetas de juegos existentes, cada una con detalles como el nombre del juego, género, descripción y mucho más. Además, la plataforma permite a los usuarios **crear nuevas tarjetas** para sus videojuegos favoritos o incluso inventar nuevos títulos. Los usuarios pueden organizar las tarjetas a través de **filtros avanzados** 🔍, permitiendo ordenar las tarjetas por categorías, nombre o género. Esta plataforma es ideal tanto para jugadores como para desarrolladores que desean compartir o descubrir más sobre los videojuegos de forma interactiva y ordenada.",
  url_repository: "https://pi-web-livid.vercel.app/",
  url_deploy: "https://pi-web-livid.vercel.app/",
  img: "https://pi-web-livid.vercel.app/",
},
{
  name: "⚙️ Aplicación de Mantenimiento para PLC Siemens",
  description:
    "Desarrollé una aplicación móvil en **C#** con **Xamarin** para **Android**, enfocada en mejorar la respuesta a fallas de equipos industriales mediante una conexión eficiente con un **PLC Siemens**. La aplicación se conecta a través de una red **WiFi privada** 🔒 para asegurar la comunicación y proteger los datos. El principal objetivo es permitir que el personal de mantenimiento reciba notificaciones oportunas 📲 cuando equipos como grúas o sistemas de traslación sufran fallas, acelerando la intervención. Además, la interfaz proporciona información detallada sobre posibles fallas y guarda todos los datos en una **base de datos** 🗄️, permitiendo generar **KPIs** 📊 para realizar un análisis más profundo y atacar el problema de raíz. Esto contribuye a mejorar la eficiencia operativa y a reducir tiempos de inactividad del equipo.",
  url_repository: "https://res.cloudinary.com/draxxv99e/image/upload/v1744856845/IMAGENES%20WEBS/RENAULT%20APP/APKRenault_pfu0mm.jpg",
  url_deploy: "https://res.cloudinary.com/draxxv99e/video/upload/v1744856847/IMAGENES%20WEBS/RENAULT%20APP/aplicacion_h7zqcv.mp4",
  img: "https://res.cloudinary.com/draxxv99e/video/upload/v1744856847/IMAGENES%20WEBS/RENAULT%20APP/aplicacion_h7zqcv.mp4",
},
{
  name: "📋 Registro Visual de Usuarios",
  description:
    "Desarrollé una aplicación moderna que permite **registrar usuarios** mediante un formulario donde se cargan datos como **nombre**, **apellido**, **correo electrónico** y una **imagen de perfil** 🧑‍💻📸. La información se almacena de forma eficiente en **MongoDB** usando la API de **Mongoose**, y luego se presenta en una **tabla interactiva** 🧾 con la opción de **filtrar por fecha y hora de subida** ⏰📅. \n\nLa interfaz fue creada con **React**, **Redux**, **Vite** y **Tailwind CSS** 🌈, garantizando un diseño limpio, responsivo y de alto rendimiento. En el backend, utilicé **Node.js** y **Express** para manejar rutas, lógica de negocio y conexión con la base de datos. Esta app es ideal para empresas que deseen llevar un registro visual ordenado de empleados, usuarios o clientes.",
  url_repository: "https://estivenarboleda-60c01.web.app/",
  url_deploy: "https://estivenarboleda-60c01.web.app/",
  img: "https://estivenarboleda-60c01.web.app/",
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

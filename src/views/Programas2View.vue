<template>
  <div style="min-height: 100vh; width: 100%">
    <section class="sub-header">
      <h1>Programas</h1>
    </section>
    <AppNavbar />
    <section class="link-section">
      <nav class="breadcrumbs">
        <ul>
          <li>
            <router-link to="/"><span>🚀</span></router-link>
          </li>
          <li><router-link to="/programas1">Programas</router-link></li>
          <li>
            <router-link to="/programas2">Programas Regionales</router-link>
          </li>
        </ul>
      </nav>
    </section>
    <section class="section-container">
      <div class="mision-vision">
        <h1 class="titulo">
          Programas Regionales
          <span class="icon">🚀 </span>
        </h1>
        <div class="content-container">
          <div class="paragraphs">
            <p>
              Los Programas Regionales fortalecen la presencia de la UCV en
              distintas comunidades del país, articulando soluciones a
              necesidades locales a través de la educación, la investigación y
              la vinculación con la sociedad. Su propósito es impulsar el
              desarrollo social, cultural y tecnológico mediante la formación
              académica, el apoyo a la innovación y la prestación de servicios
              en diversas áreas.
            </p>
            <h2>Misión</h2>
            <p>
              Promover la participación activa de la UCV en el desarrollo
              regional, coordinando programas que respondan a las necesidades de
              las comunidades en educación, salud, infraestructura y otras áreas
              clave. A través de la vinculación con distintos sectores, buscamos
              mejorar la calidad de vida y fomentar el progreso sostenible.
            </p>
            <h2>Visión</h2>
            <p>
              Ser un modelo de referencia en la gestión de programas
              universitarios para el desarrollo local, consolidando a la UCV
              como un actor clave en la transformación social y la generación de
              conocimiento al servicio de las comunidades del país.
            </p>
          </div>
        </div>
      </div>
    </section>

    <section>
      <div class="menu-global">
        <div class="row">
          <!-- Columna 1 -->
          <div class="menu-col" v-for="(item, index) in menuItems" :key="index">
            <div class="image-container">
              <img :src="item.image" alt="Imagen del menú" />
              <div class="layer">
                <div class="text-box">
                  <h3>{{ item.title }}</h3>
                  <div class="btn-container">
                    <button
                      @click="openContentBar(item.title, item.description)"
                      class="hero-btn"
                    >
                      Conoce más ⇀
                    </button>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <ContentBar
        :isVisible="isContentBarVisible"
        :title="currentTitle"
        :description="currentDescription"
        @close="closeContentBar"
      />
    </section>
    <ContactForm />
  </div>
</template>

<script>
import AppNavbar from "../components/appNavbar";
import ContentBar from "../components/content-bar.vue";
import ContactForm from "../components/ContactForm.vue";

export default {
  name: "Departamento1View",
  components: {
    AppNavbar,
    ContentBar,
    ContactForm,
  },
  data() {
    return {
      isDrawerOpen: false,
      isContentBarVisible: false,
      showContentBar: false,
      currentTitle: "",
      currentDescription: "",
      menuItems: [
        {
          image: require("@/assets/img/L.png"),
          title: "OBJETIVOS",
          subtitle: "",
          description:
            "Identificar las necesidades de desarrollo social y económico de las comunidades locales y regionales. Diseñar y ejecutar programas dentro de un marco de acción estratégico para la universidad, emanado desde la Dirección de Extensión Universitaria. Fortalecer el trabajo y la vinculación con las diversas comunidades locales y regionales, pertenecientes a los diferentes sectores.",
        },
        {
          image: require("@/assets/img/D.png"),
          title: "FUNCIONES",
          subtitle: "",
          description:
            "Realizar estudios y diagnósticos para identificar las necesidades específicas de las comunidades en las que se implementarán los programas. Diseñar y ejecutar programas y proyectos que respondan a las necesidades identificadas, en el marco de las áreas de acción establecidas. Gestionar los recursos humanos, financieros y materiales necesarios para la ejecución de los programas. Monitorear y evaluar el impacto de los programas en las comunidades, con el fin de realizar los ajustes necesarios para mejorar su efectividad. Fortalecer la vinculación con las comunidades a través de la comunicación permanente y la participación activa en la gestión de los programas. Los Programas Regionales deben difundir los resultados de sus investigaciones y evaluaciones. Esto se puede hacer a través de publicaciones, conferencias y talleres. Los Programas Regionales deben fortalecer las redes de trabajo con otras instituciones que trabajan con las comunidades.",
        },
        {
          image: require("@/assets/img/P.png"),
          title: "CONTACTO",
          subtitle: "",
          description:
            "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Veritatis, soluta hic eaque natus asperiores eligendi enim provident laborum",
        },
      ],
    };
  },
  methods: {
    openDrawer() {
      this.isDrawerOpen = true;
    },
    closeDrawer() {
      this.isDrawerOpen = false;
    },
    openContentBar(title, description) {
      this.currentTitle = title;
      this.currentDescription = description;
      this.isContentBarVisible = true;
    },
    closeContentBar() {
      this.isContentBarVisible = false;
    },
    handleClose() {
      this.showContentBar = false;
    },
    beforeEnter(el) {
      el.style.transform = "translateX(100%)";
    },
    enter(el, done) {
      el.offsetHeight; // Trigger reflow
      el.style.transition = "transform 0.3s ease-in-out";
      el.style.transform = "translateX(0)";
      done();
    },
    leave(el, done) {
      el.style.transition = "transform 0.3s ease-in-out";
      el.style.transform = "translateX(100%)";
      done();
    },
  },
};
</script>
<style scoped>
@font-face {
  font-family: "museo-sans";
  src: url("../assets/fonts/MuseoSans-100.ttf");
}
* {
  font-family: "museo-sans";
}
p {
  color: #fff;
  font-size: 20px;
  line-height: 1.6; /* Interlineado ajustado */
  text-align: justify; /* Justificar texto para mejor lectura */
  margin-bottom: 20px;
}

h3 {
  text-align: center;
  font-weight: 100;
  margin: 10px 0;
}

.sub-header {
  height: 30vh;
  width: 100%;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  background-image: linear-gradient(
      to top,
      rgba(0, 0, 0, 0.9),
      rgba(0, 0, 0, 0.1)
    ),
    url("../assets/img/graduacion.jpg");
  background-position: center;
  background-size: cover;
  text-align: center;
  color: #fff;
}
.sub-header h1 {
  padding-top: 100px;
  text-align: left;
  padding-left: 140px;
}
/* */
.link-section {
  background-color: #025247;
}

.breadcrumbs {
  font-family: "Arial", sans-serif;
  font-size: 16px;
  display: flex;
  align-items: center;
  padding: 10px 20px;
  background-color: #025247; /* Fondo claro */
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  margin-left: 100px;
}

.breadcrumbs ul {
  list-style: none;
  display: flex;
  gap: 10px; /* Espacio entre los elementos */
  margin: 0;
  padding: 0;
}

.breadcrumbs li {
  display: flex;
  align-items: center;
}

.breadcrumbs li:not(:last-child)::after {
  content: "›"; /* Separador entre enlaces */
  margin-left: 10px;
  margin-right: 10px;
  color: #ffffff; /* Color del separador */
}

.breadcrumbs a {
  text-decoration: none;
  color: #ffffff; /* Azul profesional */
  font-weight: 500; /* Peso medio */
  transition: color 0.3s;
}

.breadcrumbs a:hover {
  color: #ffffff; /* Azul más oscuro en hover */
}
/* */
.content-container {
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  gap: 20px;
  padding-bottom: 70px;
}

.icon {
  margin-right: 5px;
}

.section-container {
  width: 100%;
  background-image: linear-gradient(#01695b, #01695bef),
    url("../assets/img/deuimg.jpg");
}
.titulo {
  font-weight: 700;
  line-height: 1em;
  font-family: "museo-sans";
  padding-bottom: 20px;
  margin: 0 auto; /* Centra el contenido */
  border-bottom: 3px solid #ffffff; /* Color y grosor de la línea */
  padding-bottom: 5px; /* Espacio entre el título y la línea */
}

.mision-vision {
  padding-top: 80px;
  width: 70%;
  background-image: linear-gradient(#01695b, #01695bef),
    url("../assets/img/deuimg.jpg");
  color: #fff;
  gap: 20px;
  margin: 0 auto;
  text-align: left;
  padding: 40px 0;
}

.paragraphs {
  flex-direction: column;
  margin: 0 auto; /* Centra el contenido */
  padding-top: 40px;
}

.paragraphs p {
  font-size: 20px;
  font-weight: 300;
}
/* */

.drawer-enter-active,
.drawer-leave-active {
  transition: transform 1s ease, opacity 1s ease;
}
.drawer-enter, .drawer-leave-to /* .drawer-leave-active in <2.1.8 */ {
  transform: translateX(100%);
  opacity: 0;
}
.btn-container {
  display: none; /* Usa flexbox para alinear el contenido */
  justify-content: center; /* Centra horizontalmente */
  align-items: center; /* Centra verticalmente si es necesario */
  position: absolute;
  bottom: 20px; /* Espacio desde el borde inferior de la columna */
  left: 0; /* Alinea el contenedor al borde izquierdo de la columna */
  width: 100%; /* Asegura que el contenedor ocupe todo el ancho de la columna */
  height: auto; /* Ajusta la altura si es necesario */
  text-align: center; /* Centra el texto dentro del contenedor */
}

.menu-col:hover .btn-container {
  display: block; /* Muestra el botón al hacer hover sobre la columna */
}
.hero-btn {
  display: inline-block;
  text-decoration: none;
  color: white;
  border: 1px solid #ffffff;
  padding: 12px 34px;
  font-size: 13px;
  background: transparent;
  cursor: pointer;
  border-radius: 50px;
  width: 200px; /* Ancho del botón */
  /* margin: 0 auto; No es necesario con flexbox en el contenedor */
}
.menu-col {
  position: relative; /* Asegura que el contenedor de imagen tenga posición relativa */
  overflow: hidden;
}

.hero-btn:hover {
  background: #01695b;
  transition: 1s;
}
.row {
  display: flex;
  flex-wrap: wrap;
}

.menu-global {
  width: 100%;
  margin: 0;
  text-align: center;
  padding-top: 0px;
  overflow: hidden;
}

.row .menu-col {
  flex-basis: 33.1%;
  position: relative;
  overflow: hidden;
  padding-left: 0px;
  padding-right: 0px;
}

.menu-col img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

/* Capa negra siempre visible */
.layer {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5); /* Capa negra con 50% de opacidad */
  display: flex;
  justify-content: center;
  align-items: center;
  transition: 0.5s;
}

/* Efecto hover sobre la capa */
.layer:hover {
  background: #01695b; /* Aumenta la opacidad al hacer hover */
}

.text-box {
  color: #fff;
  text-align: center;
  padding: 20px;
  opacity: 1;
  transition: all 0.5s ease;
}

/* Efecto hover sobre el texto */
.layer:hover .text-box h3,
.layer:hover .text-box h5,
.layer:hover .text-box p {
  opacity: 0;
  transform: translateY(0);
}

.image {
  max-width: 300px;
  margin-left: 20px;
  padding-right: 20px;
  padding-bottom: 50px;
}

/** */
@media (max-width: 1024px) {
  .hero-btn {
    font-size: 18px; /* Aumenta el tamaño del botón */
  }
  h1 {
    font-size: 40px; /* Aumenta el tamaño de h1 en pantallas grandes */
  }

  .titulo {
    font-size: 40px; /* Aumenta el tamaño del título en pantallas grandes */
  }
  p {
    font-size: 20px; /* Aumenta el tamaño del texto de los párrafos */
    line-height: 1.8; /* Ajusta el interlineado */
  }

  .sub-header h1 {
    font-size: 40px; /* Aumenta el tamaño del h1 en la sección de sub-header */
  }
  .icon {
    font-size: 3rem; /* Aumenta el tamaño de los iconos */
  }
}
@media (max-width: 768px) {
  .row {
    flex-direction: column;
  }
  .menu-col {
    flex-direction: column;
  }
  .sub-header h1 {
    padding-left: 30px;
  }
  .row-about {
    flex-direction: column;
  }
  h1 {
    font-size: 1rem;
  }
  p {
    font-size: 1rem; /* Reducir tamaño aún más en pantallas muy pequeñas */
    line-height: 1.4;
    margin-bottom: 25px; /* Reducir espacio entre párrafos */
    padding: 0 5px; /* Reducir padding lateral en dispositivos más pequeños */
    text-align: left;
  }
  .icon {
    font-size: 1.5rem;
  }
  .titulo {
    font-size: 1.5rem;
  }
  .paragraphs h3 {
    font-size: 1rem;
  }
  .paragraphs p {
    font-size: 1rem;
  }
  .objetivos {
    padding-top: 80px;
    padding-bottom: 80px;
  }
  .breadcrumbs {
    margin-left: 10px;
  }
  .breadcrumbs a {
    font-size: 0.9rem;
    line-height: 1;
  }
  .mision-vision {
    padding: 20px 40px;
    width: 100%;
  }
  .sub-header {
    height: 20vh;
  }
}
</style>

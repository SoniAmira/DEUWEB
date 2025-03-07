<template>
  <div style="min-height: 100vh; width: 100%">
    <section class="sub-header">
      <h1>Sobre Nosotros</h1>
    </section>
    <AppNavbar />
    <section class="link-section">
      <nav class="breadcrumbs">
        <ul>
          <li>
            <router-link to="/"><span>🚀</span></router-link>
          </li>
          <li>
            <router-link to="/departamentos">Sobre Nosotros</router-link>
          </li>
        </ul>
      </nav>
    </section>
    <section class="section-container">
      <div class="mision-vision">
        <h1 class="titulo">Sobre Nosotros <span class="icon">🚀 </span></h1>
        <div class="content-container">
          <div class="paragraphs">
            <h2>Misión</h2>
            <p>
              Promover la transferencia de conocimientos y de tecnología, la
              acción social y la prestación de servicios para tener un impacto
              positivo en la sociedad, respondiendo a las necesidades del
              entorno y contribuyendo al desarrollo y bienestar de nuestra
              comunidad interna y externa.
            </p>
            <h2>Visión</h2>
            <p>
              Nos visualizamos como líderes en la promoción y gestión de la
              extensión universitaria, siendo reconocidos por nuestra
              contribución al desarrollo sostenible y la mejora de la calidad de
              vida de las personas en nuestra comunidad. Buscamos ser un
              referente en la generación y transferencia de conocimiento,
              estableciendo alianzas estratégicas con actores clave tanto a
              nivel nacional como internacional.
            </p>
          </div>
        </div>
      </div>
    </section>
    <section>
      <h1 class="valores">Nuestros Valores <span class="icon">🚀 </span></h1>
      <div class="card-container">
        <div class="card">
          <div class="icon">
            <img src="../assets/img/compromiso.png" alt="Icono 1" />
          </div>
          <h3 class="title">COMPROMISO</h3>
          <p class="text">
            Con el crecimiento y desarrollo de nuestra comunidad. Trabajamos de
            manera responsable, ética y dedicada para brindar oportunidades de
            aprendizaje y desarrollo a todas las personas que forman parte de
            nuestra comunidad, tanto interna como externa.
          </p>
        </div>
        <div class="card">
          <div class="icon">
            <img src="../assets/img/excelencia.png" alt="Icono 2" />
          </div>
          <h3 class="title">EXCELENCIA</h3>
          <p class="text">
            En todo lo que hacemos, desde la planificación y desarrollo de
            nuestros programas de extensión, hasta la atención que brindamos a
            colaboradores y participantes, nos esforzamos por ofrecer servicios
            de calidad y superar expectativas.
          </p>
        </div>
        <div class="card">
          <div class="icon">
            <img src="../assets/img/innovacion.png" alt="Icono 3" />
          </div>
          <h3 class="title">INNOVACIÓN</h3>
          <p class="text">
            Fomentamos la creatividad y la innovación en la extensión
            universitaria. Buscamos nuevas formas de impactar positivamente a
            nuestra comunidad, utilizando herramientas tecnológicas,
            metodologías educativas innovadoras.
          </p>
        </div>
        <div class="card">
          <div class="icon">
            <img src="../assets/img/colaboracion.png" alt="Icono 4" />
          </div>
          <h3 class="title">COLABORACIÓN</h3>
          <p class="text">
            Valoramos el trabajo en equipo y la colaboración con nuestros
            aliados. Reconocemos que juntos podemos lograr más y nos esforzamos
            por establecer alianzas estratégicas con actores clave tanto a nivel
            nacional como internacional.
          </p>
        </div>
      </div>
    </section>
    <section class="objetivos">
      <div class="row-about">
        <div class="about-col">
          <div class="about-container-img">
            <img src="../assets/img/IMAGEN_A.png" />
          </div>
        </div>
        <div class="about-col">
          <h1>Funciones</h1>
          <p>
            La Dirección de Extensión Universitaria de la UCV trabaja para
            fortalecer el vínculo entre la universidad y la sociedad a través de
            programas que promueven el desarrollo social, cultural y educativo.
            A continuación, se detallan los objetivos y funciones que guían sus
            acciones en la proyección y el impacto comunitario.
          </p>
          <div class="btn-container">
            <button @click="openDrawer" class="hero-btn">Conoce más ⇀</button>
            <transition
              name="slide"
              @before-enter="beforeEnter"
              @enter="enter"
              @leave="leave"
            >
              <Drawer v-if="isDrawerOpen" @close="closeDrawer" />
            </transition>
          </div>
        </div>
      </div>
    </section>
    <MenuBar :menuItems="menuItems" />
    <section class="objetivos">
      <div class="row-about">
        <div class="about-col">
          <div class="about-container-img">
            <img src="../assets/img/IMAGEN_B.png" />
          </div>
        </div>
        <div class="about-col">
          <h1>Reseña Historica</h1>
          <p>
            La Dirección de Extensión Universitaria ha sido clave en la conexión
            entre la universidad y la sociedad, promoviendo proyectos de
            formación continua, cooperación y desarrollo comunitario. A lo largo
            de los años, ha fortalecido su compromiso con la educación y el
            progreso social, respondiendo a las necesidades del entorno.
          </p>
          <div class="btn-container">
            <button @click="showContentBar = true" class="hero-btn">
              Conoce más ⇀
            </button>
            <ContentBar
              :isVisible="showContentBar"
              title="RESEÑA HISTORICA"
              description="La Universidad Central de Venezuela (UCV), fundada en
            1721, es la institución de educación superior más antigua del país y
            se ha destacado por su compromiso con la docencia, la investigación
            y la extensión universitaria. En 1988, se
            estableció la Comisión de Extensión con el objetivo de impulsar las
            actividades de extensión universitaria y proponer acciones que
            promovieran la integración de todas las Facultades y Dependencias.  Este esfuerzo inicial sentó las bases para una reestructuración más
            profunda que culminó el 11 de diciembre de 1995, cuando el Consejo
            Universitario aprobó la creación de la Coordinación Central de
            Extensión. Posteriormente, el 27 de noviembre de 2002, por decisión
            del Consejo Universitario, se le otorgó el rango de Dirección,
            consolidándose como la Dirección de Extensión Universitaria de la
            UCV. En noviembre de 2024, la Dirección de Extensión Universitaria celebró una jornada
            conmemorativa titulada Celebrando nuestra historia y con visión
            hacia el futuro, en el Aula Magna de la UCV.  Este evento destacó
            los logros alcanzados y reafirmó el compromiso de la dirección con
            la formación, la gestión social y la innovación. A lo largo de su historia, la Dirección de Extensión Universitaria ha sido fundamental en la consolidación de la UCV como una institución comprometida con el desarrollo integral de la sociedad venezolana, promoviendo la educación continua y la participación activa en la resolución de los desafíos sociales y culturales del país."
              @close="handleClose"
            />
          </div>
        </div>
      </div>
    </section>
    <img src="../assets/img/f_organigrama.png" class="organigrama" />
  </div>
</template>

<script>
import AppNavbar from "../components/appNavbar";
import Drawer from "../components/Sidebar.vue";
import ContentBar from "../components/content-bar.vue";
import MenuBar from "../components/MenuBar.vue";

export default {
  name: "AboutView",
  components: {
    Drawer,
    AppNavbar,
    ContentBar,
    MenuBar,
  },
  data() {
    return {
      isDrawerOpen: false,
      showContentBar: false,
      menuItems: [
        {
          image: require("@/assets/img/josephp.jpg"),
          title: "Ing. José Antonio Fernández",
          subtitle: "Sub-Director",
          description:
            "Subdirector de la Dirección de Extensión Universitaria, enfocado en fortalecer las relaciones interinstitucionales y coordinar iniciativas que impulsen la innovación y el desarrollo.",
        },
        {
          image: require("@/assets/img/mercyphp.jpg"),
          title: "Prof. Mercy Ospina",
          subtitle: "Directora",
          description:
            "Directora de la Dirección de Extensión Universitaria, comprometida con la promoción del conocimiento y la acción social para generar un impacto positivo en la comunidad universitaria y la sociedad en general.",
        },
        {
          image: require("@/assets/img/eglin1.png"),
          title: "Sra. Eglin González",
          subtitle: "Secretaria Ejecutiva",
          description:
            "Secretaria General de la Dirección de Extensión Universitaria, responsable de la organización y el soporte administrativo para garantizar el cumplimiento de los objetivos estratégicos del área.",
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
    handleClose() {
      this.showContentBar = false;
    },
  },
};
</script>

<style scoped>
* {
  font-family: museo-sans;
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
    url("../assets/img/nubes.png");
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

p {
  color: #fff;
  font-size: 20px;
  font-weight: 300;
  line-height: 1.6; /* Interlineado ajustado */
  text-align: justify; /* Justificar texto para mejor lectura */
  margin-bottom: 20px;
}

h3 {
  text-align: center;
  font-weight: 100;
  margin: 10px 0;
}
/* */
.row-about {
  display: flex;
  justify-content: center;
  gap: 100px;
}

.objetivos {
  width: 70%;
  margin: auto;
  padding-top: 150px;
  padding-bottom: 150px;
}

.about-col {
  flex-basis: 40%;
}

.about-col img {
  width: 100%;
}

.about-col p {
  color: black;
  text-align: left;
  font-weight: 500;
}

.about-col h1 {
  padding-top: 0;
  text-align: left;
  font-weight: 700;
}

.hero-btn {
  display: inline-block;
  text-decoration: none;
  color: #000000;
  border: 1px solid #000000;
  padding: 5px 23px;
  background: transparent;
  position: relative;
  cursor: pointer;
  border-radius: 50px;
}

.hero-btn:hover {
  border: 1px solid #01695b;
  background: #01695b;
  transition: 1s;
}

.btn-container {
  text-align: left;
}

.drawer-enter-active,
.drawer-leave-active {
  transition: transform 1s ease, opacity 1s ease;
}

.drawer-enter, .drawer-leave-to /* .drawer-leave-active in <2.1.8 */ {
  transform: translateX(100%);
  opacity: 0;
}

.menu-content h1 {
  width: 80%;
  margin: auto;
  color: #01695b;
  text-align: left;
  padding-top: 10px;
  padding-bottom: 30px;
}

.layer:hover .menuItems {
  background: #01695b;
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
.image {
  max-width: 300px;
  margin-left: 20px;
  padding-right: 20px;
  padding-bottom: 50px;
}

.organigrama {
  width: 90%;
  height: 90%;
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

/** */
.valores {
  font-weight: 700;
  line-height: 1em;
  font-family: "museo-sans";
  padding-bottom: 20px;
  margin: 0 auto; /* Centra el contenido */
  padding-bottom: 50px; /* Espacio entre el título y la línea */
  padding-top: 100px;
}
.card-container {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 20px;
  margin: 20px;
  width: 80%;
  margin: 20px auto;
}

.card {
  width: 23%; /* Ajusta al 23% para que quepan 4 cards horizontalmente */
  background-color: #e7e7e7; /* Cambia el color si lo deseas */
  padding: 20px;
  border-radius: 15px; /* Borde más redondeado */
  text-align: center;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2); /* Sombra más suave */
  transition: transform 0.3s ease, box-shadow 0.3s ease; /* Transiciones suaves */
  overflow: hidden;
  display: flex;
  flex-direction: column; /* Asegura que los elementos estén en columna */
  justify-content: space-between; /* Espacio distribuido entre los elementos */
}

.card:hover {
  transform: translateY(-10px); /* Efecto de elevar la tarjeta */
  box-shadow: 0 12px 24px rgba(0, 0, 0, 0.3); /* Sombra más prominente */
}

.card .icon {
  flex-shrink: 0; /* No permite que el icono se reduzca */
}

.card .icon img {
  width: 40px; /* Tamaño ligeramente mayor para los iconos */
  height: 40px;
  object-fit: contain;
  transition: transform 0.3s ease;
}

.card .icon img:hover {
  transform: scale(1.1); /* Efecto de agrandar el icono al hacer hover */
}

.card .title {
  font-size: 20px; /* Título más grande */
  font-weight: 600;
  margin-bottom: 10px;
  color: black; /* Color de título más oscuro */
  flex-grow: 0; /* Evita que el título se estire */
}

.card .text {
  font-size: 14.5px;
  color: black; /* Color de texto un poco más suave */
  text-align: left;
  line-height: 1.5; /* Mayor altura de línea para mejor legibilidad */
  flex-grow: 1; /* Permite que el texto ocupe el espacio restante */
}
/**** */
@media (max-width: 1024px) {
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

  .hero-btn {
    font-size: 18px; /* Aumenta el tamaño del botón */
  }

  .icon {
    font-size: 3rem; /* Aumenta el tamaño de los iconos */
  }
}
@media (max-width: 768px) {
  .sub-header h1 {
    padding-left: 30px;
  }
  .card {
    width: 100%; /* En pantallas pequeñas, las cards ocupan el 100% del ancho */
    margin-bottom: 20px;
  }
  .card .icon img {
    width: 40px; /* Reduce el tamaño de los iconos en pantallas más pequeñas */
    height: 40px; /* Reduce el tamaño de los iconos */
  }

  .card .title {
    font-size: 1rem; /* Reduce el tamaño del título */
  }

  .card .text {
    font-size: 1rem; /* Reduce el tamaño del texto */
  }
  .row-about {
    flex-direction: column;
  }
  h1 {
    font-size: 1.5rem;
  }
  p {
    font-size: 1rem; /* Reducir tamaño aún más en pantallas muy pequeñas */
    line-height: 1.4;
    margin-bottom: 25px; /* Reducir espacio entre párrafos */
    padding: 0 5px; /* Reducir padding lateral en dispositivos más pequeños */
  }
  .icon {
    font-size: 1.5rem;
  }
  .titulo {
    font-size: 1.5rem;
  }
  .paragraphs h2 {
    font-size: 1rem;
  }
  .paragraphs p {
    font-size: 1rem;
    text-align: left;
  }
  .hero-btn {
    font-size: 1rem; /* Aumenta el tamaño del botón */
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
    line-height: 1.5;
  }
  .mision-vision {
    padding: 20px 40px;
    width: 100%;
  }
  .sub-header {
    height: 20vh;
  }
  .row-about {
    gap: 50px;
  }
}
</style>

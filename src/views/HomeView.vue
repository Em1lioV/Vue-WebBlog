<template>
  <div>
    <h1>Home</h1>
    <button @click="showPosts = !showPosts">togle post</button>
    <button @click="posts.pop()">delete post</button>
    <PostList v-if="showPosts" :posts="posts"/>
  </div>
</template>

<script>
import PostList from '@/components/PostList.vue';
import { ref } from 'vue'


export default {
    name: 'HomeView',
    setup() {
      const posts = ref([
        { title: 'welcome to the blog', body: '<p>Bienvenido a nuestro blog de desarrollo web. Aquí encontrarás artículos informativos y consejos sobre diferentes aspectos de la programación web y el diseño de sitios.</p><p>En este primer artículo, te damos la bienvenida y esperamos que encuentres contenido útil y valioso. ¡Gracias por visitarnos!</p>', id: 1 },
        { title: 'top 5 CSS tips', body: '<p>En este artículo, compartiremos contigo cinco consejos esenciales para mejorar tus habilidades en CSS y crear diseños web impresionantes.</p><ol><li>Usa Selectores Específicos: Evita el uso de selectores demasiado generales, como <code>div</code> o <code>p</code>, ya que pueden afectar a múltiples elementos en tu página. En su lugar, utiliza selectores más específicos para aplicar estilos solo a los elementos deseados.</li><li>Mantén tu CSS Organizado: Estructura tu CSS de manera organizada y coherente. Utiliza comentarios para separar secciones y agrupa reglas de estilo relacionadas. Esto facilita la lectura y el mantenimiento del código a medida que tu proyecto crece.</li><li>Utiliza Flexbox y Grid Layout: Aprende a utilizar Flexbox y Grid Layout para el diseño de páginas web. Estas herramientas de diseño CSS proporcionan un control poderoso y flexible sobre la disposición de los elementos en tu página, lo que facilita la creación de diseños responsivos y complejos.</li><li>Optimiza para Móviles y Velocidad de Carga: Asegúrate de que tu diseño sea receptivo (responsive) para dispositivos móviles y optimiza las imágenes y archivos CSS para una carga rápida. Los tiempos de carga rápidos son esenciales para mejorar la experiencia del usuario y el SEO.</li><li>Prueba en Varios Navegadores: Realiza pruebas en diferentes navegadores y dispositivos para garantizar que tu sitio web se vea y funcione correctamente en todos ellos. Utiliza herramientas de desarrollo web como DevTools en Chrome para depurar problemas de CSS específicos del navegador.</li></ol><p>Esperamos que estos consejos te sean útiles en tu viaje de desarrollo web. ¡Mantente atento a más artículos informativos!</p>', id: 2 },
        { title: 'CSS best practices', body: '<p>En este artículo, exploraremos algunas de las mejores prácticas en CSS que te ayudarán a escribir código más limpio y mantenible.</p><ol><li>Nombres Significativos de Clases: Asigna nombres significativos a tus clases CSS para que otros desarrolladores (y tú mismo en el futuro) puedan entender fácilmente su propósito.</li><li>Evita !important: El uso excesivo de la propiedad <code>!important</code> puede hacer que tu código sea difícil de mantener. Utilízalo con moderación y considera estructurar tu CSS de manera que no sea necesario.</li><li>Separación de Responsabilidades: Sigue el principio de separación de responsabilidades, donde el HTML se encarga de la estructura, el CSS de la presentación y JavaScript de la interacción. Esto facilita la colaboración y el mantenimiento del código.</li><li>Optimiza Imágenes: Comprime y optimiza las imágenes para la web. Utiliza formatos adecuados y dimensiones apropiadas para reducir el tiempo de carga.</li><li>Usa Preprocesadores CSS: Considera el uso de preprocesadores CSS como Sass o Less para simplificar y mejorar la legibilidad de tu código CSS.</li></ol><p>Esperamos que estas mejores prácticas te ayuden a escribir CSS más eficiente y fácil de mantener.</p>', id: 3 },
        { title: 'Mastering CSS Layouts', body: '<p>En este artículo, profundizaremos en el dominio de los diseños CSS, explorando técnicas avanzadas para lograr diseños complejos y personalizados.</p><ul><li>Flexbox Avanzado: Exploraremos casos de uso más avanzados de Flexbox, como la creación de diseños complejos de dos dimensiones.</li><li>Grid Layout Avanzado: Profundizaremos en Grid Layout y cómo puedes usarlo para crear diseños sofisticados y adaptativos.</li><li>Diseño de Páginas Multipantalla: Discutiremos cómo abordar el diseño de páginas que deben funcionar en una variedad de dispositivos y tamaños de pantalla.</li><li>Animaciones y Transiciones CSS: Aprenderás a crear animaciones y transiciones suaves y atractivas utilizando CSS.</li><li>Compatibilidad con Navegadores Antiguos: Exploraremos estrategias para garantizar que tus diseños funcionen en navegadores más antiguos.</li></ul><p>Esperamos que este artículo te ayude a llevar tus habilidades de diseño CSS al siguiente nivel.</p>', id: 4 },
        { title: 'Responsive Web Design with CSS', body: '<p>En este artículo, te sumergirás en el mundo del diseño web receptivo (responsive) y cómo puedes lograr que tu sitio web se vea y funcione de manera óptima en una variedad de dispositivos y tamaños de pantalla.</p><ul><li>Media Queries: Cómo utilizar media queries para aplicar estilos específicos según las características del dispositivo.</li><li>Imágenes Responsivas: Técnicas para cargar imágenes de manera eficiente en diferentes dispositivos.</li><li>Viewport Units: Cómo usar unidades de viewport (vw, vh, vmin, vmax) para crear diseños adaptativos.</li><li>Frameworks Receptivos: Una introducción a los frameworks CSS receptivos como Bootstrap y Foundation.</li><li>Pruebas y Depuración: Herramientas y estrategias para probar y depurar sitios web receptivos.</li></ul><p>Esperamos que este artículo te proporcione una base sólida para crear sitios web que ofrezcan una experiencia óptima en todos los dispositivos.</p>', id: 5 }
      ])

      const showPosts = ref(true)


      return {posts,showPosts}
    },
    components: { PostList }
}
</script>

  <template>
    <div class="flex flex-col items-center justify-center min-h-screen bg-blue-100 text-center">
      <h1 class="heading text-4xl font-bold text-blue-700 mb-4">Welcome to My Vue App!</h1>
      <p class="paragraph text-lg text-gray-600 mb-4">This is a sample app using Vue 3, TypeScript, and Tailwind CSS.</p>
      <i class="icon fas fa-info-circle fa-lg mr-2 text-blue-600"></i>
    </div>
  </template>

  <script lang="ts">
  import { defineComponent, onMounted } from 'vue';
  import { gsap } from 'gsap';

  export default defineComponent({
    name: 'WelcomeComponent',
    setup() {
      onMounted(() => {
        // Create a GSAP timeline
        const tl = gsap.timeline();

        // Add animations using class selectors
        tl.from(".heading", { duration: 1, opacity: 0, y: -50, yoyo:true,repeat:-1 }) // Fade in the heading from the top
          .from(".paragraph", { duration: 1, opacity: 0, y: 50 }, "-=0.5") // Fade in the paragraph from the bottom
          .from(".icon", { duration: 1, opacity: 0, scale: 0 }, "-=0.5"); // Fade and scale in the icon
      });
    },
  });
  </script>

  <style scoped>
  </style>

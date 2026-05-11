<template>
  <div
    class="bg-slate-900 text-slate-400 selection:bg-teal-300 selection:text-teal-900 min-h-screen font-sans leading-relaxed"
  >
    <!-- Background Spotlight Effect -->
    <div
      class="fixed inset-0 z-30 pointer-events-none lg:block hidden"
      :style="{
        background: `radial-gradient(600px at ${mouseX}px ${mouseY}px, rgba(29, 78, 216, 0.15), transparent)`,
      }"
    ></div>

    <div
      class="mx-auto min-h-screen max-w-screen-xl px-6 py-12 md:px-12 md:py-20 lg:px-24 lg:py-0"
    >
      <div
        class="lg:flex lg:justify-between lg:gap-4 divide-y divide-teal-300/20 lg:divide-y-0 lg:divide-x"
      >
        <!-- LEFT COLUMN: Fixed Header -->
        <header
          class="lg:sticky lg:top-0 lg:flex lg:max-h-screen lg:w-1/2 lg:flex-col lg:justify-between lg:py-24"
        >
          <div>
            <img
              src="https://avatars.githubusercontent.com/u/122380441?v=4"
              alt="Lindokuhle Mtengwane"
              class="w-30 h-30 rounded-4xl mb-4"
            />
          </div>
          <div>
            <h1
              class="text-4xl font-bold tracking-tight text-slate-200 sm:text-3lg"
            >
              <a href="/">Lindokuhle Mtengwane</a>
            </h1>
            <div
              class="mt-3 inline-flex items-center rounded-full bg-teal-400/10 px-4 py-2 text-md font-medium leading-5 text-teal-300"
            >
              <h2>Frontend Developer</h2>
            </div>
            <p class="mt-4 max-w-xs leading-normal">
              I craft clean, responsive, and pixel-perfect digital experiences
              that bring ideas to life on the web.
            </p>

            <nav class="nav hidden lg:block" aria-label="In-page jump links">
              <ul class="mt-16 w-max">
                <li v-for="item in navItems" :key="item.href">
                  <a
                    class="group flex items-center py-3"
                    :href="item.href"
                    @click="activeSection = item.id"
                  >
                    <span
                      class="nav-indicator mr-4 h-px transition-all group-hover:w-16 group-hover:bg-slate-200 group-focus-visible:w-16 group-focus-visible:bg-slate-200"
                      :class="
                        activeSection === item.id
                          ? 'w-16 bg-slate-200'
                          : 'w-8 bg-slate-600'
                      "
                    ></span>
                    <span
                      class="nav-text text-xs font-bold uppercase tracking-widest group-hover:text-slate-200 group-focus-visible:text-slate-200"
                      :class="
                        activeSection === item.id
                          ? 'text-slate-200'
                          : 'text-slate-500'
                      "
                    >
                      {{ item.label }}
                    </span>
                  </a>
                </li>
              </ul>
            </nav>
          </div>

          <ul
            class="ml-1 mt-8 flex items-center gap-5"
            aria-label="Social media"
          >
            <li>
              <a
                class="block hover:text-slate-200 transition-colors"
                href="https://github.com/LindokuhleMtengwane"
                target="_blank"
                rel="noreferrer"
              >
                <span class="sr-only">GitHub</span>
                <Github :size="24" />
              </a>
            </li>
            <li>
              <a
                class="block hover:text-slate-200 transition-colors"
                href="https://linkedin.com/in/lindokuhle-mtengwane"
                target="_blank"
                rel="noreferrer"
              >
                <span class="sr-only">LinkedIn</span>
                <Linkedin :size="24" />
              </a>
            </li>
            <li>
              <a
                class="block hover:text-slate-200 transition-colors"
                href="mailto:lindokuhlemtengwane@gmail.com"
                target="_blank"
                rel="noreferrer"
              >
                <span class="sr-only">Mail</span>
                <Mail :size="24" />
              </a>
            </li>
          </ul>
        </header>

        <!-- RIGHT COLUMN: Scrolling Content -->
        <main class="pt-24 lg:w-1/2 lg:py-24">
          <!-- ABOUT SECTION -->
          <section
            id="about"
            class="mb-16 scroll-mt-16 md:mb-24 lg:mb-36 lg:scroll-mt-24 section-target"
          >
            <div
              class="sticky top-0 z-20 -mx-6 mb-4 w-screen bg-slate-900/75 px-6 py-5 backdrop-blur md:-mx-12 md:px-12 lg:sr-only lg:relative lg:top-auto lg:mx-auto lg:w-full lg:px-0 lg:py-0 lg:opacity-0"
            >
              <h2
                class="text-sm font-bold uppercase tracking-widest text-slate-200 lg:sr-only"
              >
                About
              </h2>
            </div>

            <h2
              class="inline-flex items-center rounded-full bg-teal-400/10 px-4 py-2 text-mg font-medium leading-5 text-white mb-4"
            >
              Get to Know Me
            </h2>

            <div class="space-y-4">
              <p>
                I’m a front-end developer passionate about building clean,
                responsive, and user-friendly digital experiences. I enjoy
                creating intuitive interfaces that not only look modern but also
                feel seamless and accessible across different devices. I
                specialize in turning ideas into interactive web applications
                using technologies like
                <strong class="text-slate-200 font-medium"
                  >JavaScript, Vue.js, React, HTML, and CSS</strong
                >. I pay close attention to the small details that improve
                usability and believe the best products are built where
                thoughtful design meets scalable, maintainable code.
              </p>
              <p>
                Currently, I focus on developing modern web applications,
                integrating
                <strong class="text-slate-200 font-medium">RESTful APIs</strong
                >,
                <strong class="text-slate-200 font-medium">WebSockets</strong>
                and real-time features, and creating smooth user experiences
                with clean front-end architecture. My experience ranges from
                responsive landing pages to dynamic web applications, allowing
                me to adapt to different project needs and environments.
              </p>
              <p>
                Outside of coding, I enjoy reading, hiking, exploring nature,
                and finding inspiration through creativity and exploring new
                UI/UX design trends or refining my workflow with tools like
                Tailwind CSS and the Adobe Creative Suite.
              </p>
            </div>
          </section>

          <!-- EXPERIENCE SECTION -->
          <section
            id="experience"
            class="mb-16 scroll-mt-16 md:mb-24 lg:mb-36 lg:scroll-mt-24 section-target"
          >
            <div
              class="sticky top-0 z-20 -mx-6 mb-4 w-screen bg-slate-900/75 px-6 py-5 backdrop-blur md:-mx-12 md:px-12 lg:sr-only lg:relative lg:top-auto lg:mx-auto lg:w-full lg:px-0 lg:py-0 lg:opacity-0"
            >
              <h2
                class="text-sm font-bold uppercase tracking-widest text-slate-200 lg:sr-only"
              >
                Experience
              </h2>
            </div>
            <h2
              class="inline-flex items-center rounded-full bg-teal-400/10 px-4 py-2 text-mg font-medium leading-5 text-white mb-8"
            >
              Experience
            </h2>

            <div class="group/list">
              <div v-for="job in experience" :key="job.company" class="mb-12">
                <div
                  class="group relative grid pb-1 transition-all sm:grid-cols-8 sm:gap-8 md:gap-4 lg:hover:!opacity-100 lg:group-hover/list:opacity-50"
                >
                  <div
                    class="absolute -inset-x-4 -inset-y-4 z-0 hidden rounded-md transition motion-reduce:transition-none lg:-inset-x-6 lg:block lg:group-hover:bg-slate-800/50 lg:group-hover:shadow-[inset_0_1px_0_0_rgba(148,163,184,0.1)] lg:group-hover:drop-shadow-lg"
                  ></div>
                  <header
                    class="z-10 mb-2 mt-1 text-xs font-semibold uppercase tracking-wide text-slate-500 sm:col-span-2"
                  >
                    {{ job.date }}
                  </header>
                  <div class="z-10 sm:col-span-6">
                    <h3 class="font-medium leading-snug text-slate-200">
                      <div>
                        <a
                          class="inline-flex items-baseline font-medium leading-tight text-slate-200 hover:text-teal-300 focus-visible:text-teal-300 group/link text-base"
                        >
                          <span
                            class="absolute -inset-x-4 -inset-y-2.5 hidden rounded md:-inset-x-6 md:-inset-y-4 lg:block"
                          ></span>
                          <span
                            >{{ job.role }} ·
                            <span class="inline-block"
                              >{{ job.company }}
                              <ExternalLink
                                :size="14"
                                class="inline-block ml-1 translate-y-px transition-transform group-hover/link:-translate-y-1 group-hover/link:translate-x-1" /></span
                          ></span>
                        </a>
                      </div>
                    </h3>
                    <p class="mt-2 text-sm leading-normal">
                      {{ job.description }}
                    </p>
                    <ul
                      class="mt-2 flex flex-wrap"
                      aria-label="Technologies used"
                    >
                      <li
                        v-for="tech in job.tech"
                        :key="tech"
                        class="mr-1.5 mt-2"
                      >
                        <div
                          class="flex items-center rounded-full bg-teal-400/10 px-3 py-1 text-xs font-medium leading-5 text-teal-300"
                        >
                          {{ tech }}
                        </div>
                      </li>
                    </ul>
                  </div>
                </div>
              </div>
            </div>

            <div class="mt-12">
              <a
                class="inline-flex items-baseline font-medium leading-tight text-slate-200 hover:text-teal-300 focus-visible:text-teal-300 group/link text-base"
                href="/resume.pdf"
                target="_blank"
              >
                <span
                  >View Full
                  <span class="whitespace-nowrap"
                    >Resume<ArrowUpRight
                      :size="16"
                      class="inline-block ml-1 transition-transform group-hover/link:-translate-y-1 group-hover/link:translate-x-1" /></span
                ></span>
              </a>
            </div>
          </section>

          <!-- SKILLS SECTION -->
          <section
            id="skills"
            class="mb-16 scroll-mt-16 md:mb-24 lg:mb-36 lg:scroll-mt-24 section-target"
          >
            <div
              class="sticky top-0 z-20 -mx-6 mb-4 w-screen bg-slate-900/75 px-6 py-5 backdrop-blur md:-mx-12 md:px-12 lg:sr-only lg:relative lg:top-auto lg:mx-auto lg:w-full lg:px-0 lg:py-0 lg:opacity-0"
            >
              <h2
                class="text-sm font-bold uppercase tracking-widest text-slate-200 lg:sr-only"
              >
                Skills
              </h2>
            </div>
            <h2
              class="inline-flex items-center rounded-full bg-teal-400/10 px-4 py-2 text-mg font-medium leading-5 text-white mb-8"
            >
              Technical Skills
            </h2>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
              <div>
                <h4
                  class="text-slate-200 mb-4 text-xs font-bold uppercase tracking-widest"
                >
                  Frontend
                </h4>
                <div class="flex flex-wrap gap-2">
                  <span
                    v-for="s in skills.frontend"
                    :key="s"
                    class="flex items-center rounded-full bg-slate-800/50 border border-slate-700 px-3 py-1 text-xs font-medium text-slate-300"
                    >{{ s }}</span
                  >
                </div>
              </div>
              <div>
                <h4
                  class="text-slate-200 mb-4 text-xs font-bold uppercase tracking-widest"
                >
                  Backend & Tools
                </h4>
                <div class="flex flex-wrap gap-2">
                  <span
                    v-for="s in skills.backend"
                    :key="s"
                    class="flex items-center rounded-full bg-slate-800/50 border border-slate-700 px-3 py-1 text-xs font-medium text-slate-300"
                    >{{ s }}</span
                  >
                </div>
              </div>

              <div>
                <h4
                  class="text-slate-200 mb-4 text-xs font-bold uppercase tracking-widest"
                >
                  Design
                </h4>
                <div class="flex flex-wrap gap-2">
                  <span
                    v-for="s in skills.Design"
                    :key="s"
                    class="flex items-center rounded-full bg-slate-800/50 border border-slate-700 px-3 py-1 text-xs font-medium text-slate-300"
                    >{{ s }}</span
                  >
                </div>
              </div>
            </div>
          </section>

          <!-- PROJECTS SECTION -->
          <section
            id="projects"
            class="mb-16 scroll-mt-16 md:mb-24 lg:mb-36 lg:scroll-mt-24 section-target"
          >
            <div
              class="sticky top-0 z-20 -mx-6 mb-4 w-screen bg-slate-900/75 px-6 py-5 backdrop-blur md:-mx-12 md:px-12 lg:sr-only lg:relative lg:top-auto lg:mx-auto lg:w-full lg:px-0 lg:py-0 lg:opacity-0"
            >
              <h2
                class="text-sm font-bold uppercase tracking-widest text-slate-200 lg:sr-only"
              >
                Projects
              </h2>
            </div>
            <h2
              class="inline-flex items-center rounded-full bg-teal-400/10 px-4 py-2 text-lg font-medium leading-5 text-white mb-8"
            >
              Projects
            </h2>

            <div class="group/list">
              <div v-for="project in projects" :key="project[0]" class="mb-12">
                <div
                  class="group relative grid pb-1 transition-all sm:grid-cols-8 sm:gap-8 md:gap-4 lg:hover:!opacity-100 lg:group-hover/list:opacity-50"
                >
                  <div
                    class="absolute -inset-x-4 -inset-y-4 z-0 hidden rounded-md transition motion-reduce:transition-none lg:-inset-x-6 lg:block lg:group-hover:bg-slate-800/50 lg:group-hover:shadow-[inset_0_1px_0_0_rgba(148,163,184,0.1)] lg:group-hover:drop-shadow-lg"
                  ></div>
                  <div class="z-10 sm:col-span-3">
                    <!-- Project Image -->
                    <a
                      :href="project[3]"
                      target="_blank"
                      class="block overflow-hidden rounded-md"
                    >
                      <img
                        :src="project[4]"
                        :alt="project[0]"
                        class="w-full h-30 object-cover hover:opacity-80 transition-opacity"
                      />
                    </a>
                  </div>
                  <div class="z-10 sm:col-span-5">
                    <h3 class="font-medium leading-snug text-slate-200">
                      <a
                        :href="project[3]"
                        target="_blank"
                        class="inline-flex items-baseline font-medium leading-tight text-slate-200 hover:text-teal-300 focus-visible:text-teal-300 group/link text-base"
                      >
                        <span
                          class="absolute -inset-x-4 -inset-y-2.5 hidden rounded md:-inset-x-6 md:-inset-y-4 lg:block"
                        ></span>
                        <span>{{ project[0] }}</span>
                      </a>
                    </h3>
                    <p class="mt-2 text-sm leading-normal">
                      {{ project[1] }}
                    </p>
                    <ul
                      class="mt-2 flex flex-wrap"
                      aria-label="Technologies used"
                    >
                      <li
                        v-for="tech in project[2]"
                        :key="tech"
                        class="mr-1.5 mt-2"
                      >
                        <div
                          class="flex items-center rounded-full bg-teal-400/10 px-3 py-1 text-xs font-medium leading-5 text-teal-300"
                        >
                          {{ tech }}
                        </div>
                      </li>
                    </ul>
                  </div>
                </div>
              </div>
            </div>
          </section>
          <!-- FOOTER -->
          <!-- <footer class="max-w-md pb-16 text-sm text-slate-500 sm:pb-0">
            <p>
              Coded in <a href="https://code.visualstudio.com/" class="font-medium text-slate-400 hover:text-teal-300 focus-visible:text-teal-300">Visual Studio Code</a>. Built with <a href="https://vuejs.org/" class="font-medium text-slate-400 hover:text-teal-300 focus-visible:text-teal-300">Vue.js</a> and <a href="https://tailwindcss.com/" class="font-medium text-slate-400 hover:text-teal-300 focus-visible:text-teal-300">Tailwind CSS</a>, deployed with <a href="https://cloud.google.com/run" class="font-medium text-slate-400 hover:text-teal-300 focus-visible:text-teal-300">Cloud Run</a>.
            </p>
          </footer> -->
        </main>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";
import {
  Github,
  Linkedin,
  Mail,
  ExternalLink,
  ArrowUpRight,
} from "lucide-vue-next";

const mouseX = ref(0);
const mouseY = ref(0);
const activeSection = ref("about");

const navItems = [
  { id: "about", label: "About", href: "#about" },
  { id: "experience", label: "Experience", href: "#experience" },
  { id: "skills", label: "Skills", href: "#skills" },
  { id: "projects", label: "Projects", href: "#projects" },
];

const experience = [
  {
    date: "2024 — 2026",
    role: "Software Developer",
    company: "PitchPrint",
    description:
      "Lead the development of production web applications using Vue.js and PHP. Architected real-time chatbot interfaces and integrated WebSocket services for dynamic, multi-user functionality. Improved site performance and maintainability through modular component design.",
    tech: [
      "Vue.js",
      "React",
      "JavaScript",
      "PHP",
      "Tailwind CSS",
      "WebSockets",
      "REST APIs",
    ],
  },
  {
    date: "2019 — 2020",
    role: "UI/UX Designer",
    company: "Humanise Designs",
    description:
      "Envisioned and executed end-to-end product development strategies, including branding and marketing assets. Created highly interactive landing pages using HTML, CSS, and JavaScript. Leveraged the Adobe Creative Suite for high-fidelity prototyping and visual design.",
    tech: ["Adobe Suite", "HTML5", "CSS3", "JavaScript", "UI/UX Design"],
  },
  {
    date: "2023 — 2024",
    role: "Customer Service Representative",
    company: "Amazon",
    description:
      "Provided specialized technical support and account troubleshooting for US-based clients. Analyzed complex user issues to deliver streamlined solutions, ensuring a positive global customer experience.",
    tech: ["Technical Support", "Troubleshooting", "CRM Systems"],
  },
];

const skills = {
  frontend: ["Vue.js", "React", "JavaScript", "Tailwind CSS", "HTML5", "CSS3"],
  backend: [
    "PHP",
    "Node.js",
    "REST APIs",
    "MySQL",
    "WordPress",
    "Shopify",
    "WebSockets",
    "Git",
    "Github",
  ],

  Design: [
    "Figma",
    "Adobe XD",
    "Illustrator",
    "Photoshop",
    "Adobe Suite",
    "UI/UX Design",
  ],
};

const projects = [
  [
    "Cache Bank",
    "A modern, responsive banking dashboard built with HTML, Tailwind CSS, and JavaScript. Features real-time transaction updates, interactive charts, and a sleek user interface for managing finances.",
    ["JavaScript", "Tailwind CSS", "HTML5"],
    "https://cache-bank.netlify.app",
    "https://via.placeholder.com/500x300?text=Project+1",
  ],
  [
    "Van Life",
    "A responsive blog template for van life enthusiasts, built with React, Tailwind CSS, and JavaScript. Showcases travel stories, tips, and a gallery of van conversions with a clean, modern design.",
    ["React", "JavaScript", "Tailwind CSS"],
    "https://example.com/project",
    "https://via.placeholder.com/500x300?text=Project+2",
  ],
  [
    "Project Name",
    "Brief description of the project.",
    ["Tech1", "Tech2", "Tech3"],
    "https://example.com/project",
    "https://via.placeholder.com/500x300?text=Project+3",
  ],
];

const handleMouseMove = (e) => {
  mouseX.value = e.clientX;
  mouseY.value = e.clientY;
};

const handleScroll = () => {
  const sections = document.querySelectorAll(".section-target");
  let current = "about";

  sections.forEach((section) => {
    const sectionTop = section.offsetTop;
    if (window.pageYOffset >= sectionTop - 100) {
      current = section.getAttribute("id");
    }
  });

  activeSection.value = current === "projects" ? "projects" : current;
};

onMounted(() => {
  window.addEventListener("mousemove", handleMouseMove);
  window.addEventListener("scroll", handleScroll);
});

onUnmounted(() => {
  window.removeEventListener("mousemove", handleMouseMove);
  window.removeEventListener("scroll", handleScroll);
});
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap");

:root {
  font-family: "Inter", sans-serif;
}

html {
  scroll-behavior: smooth;
}

body {
  margin: 0;
  -webkit-font-smoothing: antialiased;
}

/* Custom scrollbar for a cleaner look */
::-webkit-scrollbar {
  width: 8px;
}

::-webkit-scrollbar-track {
  background: #0f172a;
}

::-webkit-scrollbar-thumb {
  background: #334155;
  border-radius: 10px;
}

::-webkit-scrollbar-thumb:hover {
  background: #475569;
}
</style>

<script>
  import { mode } from "./shared.svelte";
  import Spacer from "./lib/Spacer.svelte";
  import Container from "./lib/Container.svelte";
  import Header from "./lib/Header.svelte";
  import Hero from "./lib/Hero.svelte";
  import Projects from "./lib/Projects.svelte";
  import SectionDiv from "./lib/SectionDiv.svelte";
  import Grid from "./lib/Grid.svelte";
  import Experience from "./lib/Experience.svelte";
  import Contact from "./lib/Contact.svelte";
  import Footer from "./lib/Footer.svelte";

  let projects = [
    {
      date: "01",
      title: "Lorem",
      link: "/",
      description:
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco.",
    },
    {
      date: "02",
      title: "Accusamus et",
      link: "/",
      description:
        "At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident.",
    },
  ];

  let experience = [
    {
      num: "01",
      title: "Et harum",
      role: "Role",
      description:
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco.",
    },
    {
      num: "02",
      title: "Sed ut perspiciatis",
      role: "Role",
      description:
        "Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia.",
    },
    {
      num: "03",
      title: "Omnis iste",
      role: "Role",
      description:
        "Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia.",
    },

    {
      num: "04",
      title: "Nemo enim",
      role: "Role",
      description:
        "At vero eos et accusamus et iusto odio dignissimos ducimus qui blanditiis praesentium voluptatum deleniti atque corrupti quos dolores et quas molestias excepturi sint occaecati cupiditate non provident.",
    },
  ];
</script>

<Container>
  <Header
    GridChange={(newGrid) => {
      mode.grid = newGrid;
    }}
    themeChange={(newTheme) => {
      mode.theme = newTheme;
    }}
  />
  <Hero></Hero>
  <Spacer height="7rem"></Spacer>

  <SectionDiv center="Projects" right={projects.length}></SectionDiv>
  {#each projects as project}
    <Projects {project}></Projects>
  {/each}
  <Spacer height="7rem"></Spacer>

  <SectionDiv center="Experience" right="4"></SectionDiv>
  {#each experience as exp}
    <Experience {exp}></Experience>
  {/each}
  <Spacer height="7rem"></Spacer>

  <SectionDiv center="Contact" right=""></SectionDiv>
  <Contact></Contact>

  <Spacer height="7rem"></Spacer>
  <Footer></Footer>
</Container>

<style>
</style>

<script lang="ts">
    import { t, isLoading, locale, locales } from 'svelte-i18n';
    import Nav from './components/Nav.svelte';
    import Header from './components/Header.svelte';
    import Section from './components/Section.svelte';

    // sections
    import About from './components/sections/About.svelte';
    import Skill from './components/sections/Skill.svelte';
    import Project from './components/sections/Project.svelte';
    import Blog from './components/sections/Blog.svelte';
    import Testmonial from './components/sections/Testmonial.svelte';
    import Footer from './components/Footer.svelte';
    import ContactMe from './components/sections/ContactMe.svelte';

    isLoading.subscribe((val) => {
        if (!val) {
            const splash = document.querySelector('#splashScreen');
            splash.parentNode.removeChild(splash);
        }
    });
</script>

<main>
    {#if $isLoading}
        <h1 class="text-3xl uppercase">Loading</h1>
    {:else}
        <Nav />

        <div id="container" class="">
            <Header />

            <Section sectionId="about">
                <About />
            </Section>

            <Section sectionId="skill">
                <Skill />
            </Section>

            <Section sectionId="my_projects">
                <Project />
            </Section>

            <Section sectionId="testmonial" showTilte={false}>
                <Testmonial />
            </Section>

            <Section sectionId="blog">
                <Blog />
            </Section>

            <Section sectionId="contact_me" showTilte={false}>
                <ContactMe />
            </Section>

            <Footer />
        </div>
    {/if}
</main>

<style>
    /* main {
    } */
</style>

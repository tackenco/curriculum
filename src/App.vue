<script setup>
import PageMenu from "@/components/PageMenu.vue";
import PageHead from "@/components/PageHead.vue";
import TheAside from "@/components/TheAside.vue";
import PersonalSection from "@/components/aside/PersonalSection.vue";
import TheContent from "@/components/TheContent.vue";
import AboutMe from "@/components/content/AboutMe.vue";
import BulletList from "@/components/aside/BulletList.vue";
import WorkExperience from "@/components/content/WorkExperience.vue";
import persona from '@/content/persona.json'
import skills from '@/content/skills.json'
import tools from '@/content/tools.json'
import stack from '@/content/stack.json'
import interests from '@/content/interests.json'
import jobs from '@/content/experience.json'
</script>

<template>
  <header class="sticky-top">
    <PageMenu :name="persona.name" :email="persona.email" :linkedin="persona.linkedin"/>
  </header>

  <main>
    <div class="container">
      <div class="row">
        <PageHead :name="persona.name" :title="persona.function" :photo="persona.pathToPhoto"/>
      </div>

      <div class="row">
        <TheAside>
          <PersonalSection
              title="Personal"
              :name="persona.name"
              :date-of-birth="persona.dateOfBirth"
              :domicile="persona.domicile"
              :country="persona.country"
              :email="persona.email"
              :linkedin="persona.linkedin"
          />
          <BulletList
              title="Skills"
              :items="skills"/>
          <BulletList
              title="Tools"
              :items="tools"/>
          <BulletList
              title="Stack"
              :items="stack"/>
          <BulletList
              title="Interests"
              :items="interests"/>
        </TheAside>
        <TheContent>
          <AboutMe/>
          <WorkExperience :jobs="jobs"/>
        </TheContent>
      </div>
    </div>
  </main>
</template>

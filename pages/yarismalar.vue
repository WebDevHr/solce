<template>
    <div>
        <div>
            <div class="bg-[url('/pictures/yarismalar-header-image.webp')] bg-cover bg-center relative">
                <NuxtParticles id="tsparticles11" :options="options"></NuxtParticles>
                <div class="bg-black/30">
                    <PagesHeader />
                    <BreadCrumbsVue />
                </div>
            </div>
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-20">
                <ChallengesHowItWorks />
                <ChallengesListOfChallenges />
            </div>
        </div>
    </div>
</template>
  
<script setup>
import options from '~/assets/particles/particles-color.json'

import { loadFull } from 'tsparticles'
if (process.client) {
    await loadFull(tsParticles)
}
</script>
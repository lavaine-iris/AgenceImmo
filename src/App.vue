<template>
  <nav>
    <h4 class="text-xl">
      <Bars3Icon class="inline-block h-5 w-5 text-blue-500" />
      menu (dans <code class="font-mono">/src/App.vue</code>)
    </h4>
    <ul>
      <li>
        <router-link class="text-red-600 underline font-mono" to="/">
          Accueil
        </router-link>
      </li>
      <li>
        <router-link class="text-red-600 underline font-mono" to="/simple">
          Page simple
        </router-link>
      </li>
      <li>
        <router-link class="text-red-600 underline font-mono" to="/liste">
          Liste
        </router-link>
      </li>
      <li>
        <router-link class="text-red-600 underline font-mono" to="/liste-fetch">
          Liste Fetch
        </router-link>
      </li>
      <li>
        <router-link class="text-red-600 underline font-mono" to="/edit/new">
          Formulaire Offre Maison
        </router-link>
      </li>
    </ul>
  </nav>

  <Suspense>
    <router-view class="m-2 border-2 p-2" />
    <template #fallback> Loading... </template>
  </Suspense>

  <!-- Affiche les pages -->
</template>

<script setup lang="ts">
import { Bars3Icon } from '@heroicons/vue/20/solid'
</script>

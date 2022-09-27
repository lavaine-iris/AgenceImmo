<template>
  <nav class="p-5">
    <h4 class="text-xl">
      <Bars3Icon class="inline-block h-5 w-5 text-blue-800" />
    </h4>
    <ul>
      <li>
        <router-link class="text-gray-600 font-medium" to="/">
          Accueil
        </router-link>
      </li>
      <li>
        <router-link class="text-gray-600 font-medium" to="/simple">
          Page simple
        </router-link>
      </li>
      <li>
        <router-link class="text-gray-600 font-medium" to="/liste">
          Liste
        </router-link>
      </li>
      <li>
        <router-link class="text-gray-600 font-medium" to="/liste-fetch">
          Liste Fetch
        </router-link>
      </li>
      <li>
        <router-link class="text-gray-600 font-medium" to="/edit/new">
          Formulaire Offre Maison
        </router-link>
      </li>
      <li>
        <router-link class="text-gray-600 font-medium" to="/liste-supabase">
          Liste SUPABASE
        </router-link>
      </li>
      <li>
        <router-link class="text-gray-600 font-medium" to="/login-logout">
          Créer un compte / Se connecter
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

<template>
  <div class="home">
    <h1 class="subheading grey--text">Team</h1>
    <v-container fluid class="my-5">
      <v-expansion-panels>
        <v-expansion-panel v-for="(item,i) in 5" :key="i">
          <v-expansion-panel-header>Item {{i}}</v-expansion-panel-header>
          <v-expansion-panel-content>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</v-expansion-panel-content>
        </v-expansion-panel>
      </v-expansion-panels>
    </v-container>
  </div>
</template>
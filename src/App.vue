<template>
  <v-app theme="dark">
    <v-main>
      <v-navigation-drawer rail expand-on-hover>
        <v-list nav>
          <v-list-item 
            prepend-icon="mdi-application-brackets"
            title="Dashboard"
            value="dashboard">
          </v-list-item>
          <v-list-item 
            prepend-icon="mdi-account-box-outline"
            title="Account"
            value="account">
          </v-list-item>
          <v-divider></v-divider>
          <v-list-item 
            prepend-icon="mdi-logout"
            title="Logout"
            value="logout">
          </v-list-item>
        </v-list>
      </v-navigation-drawer>

      <GraphTest></GraphTest>

    </v-main>
  </v-app>
</template>

<script setup>



</script>

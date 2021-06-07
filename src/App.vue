<template>
  <v-app>
    <v-card width="400" class="mx-auto mt-5">
      <v-card-title primary-title>
        <h1 class="display-1">Login</h1>
      </v-card-title>
      <v-card-text>
        <v-form>
          <v-text-field
            name="username"
            label="Username"
            prepend-icon="mdi-account-tie"
          ></v-text-field>
          <v-text-field
            name="name"
            label="Enter your password"
            hint="At least 8 characters"
            min="8"
            placeholder="Password"
            :type="showPassword ? 'text' : 'password'"
            prepend-icon="mdi-lock"
            :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
            @click:append="showPassword = !showPassword"
          ></v-text-field>
          <v-divider></v-divider>
          <v-card-actions>
            <v-btn color="success">Register</v-btn>
            <v-spacer></v-spacer>
            <v-btn color="info">Login</v-btn>
          </v-card-actions>
          <v-card-actions>
            <h2>Button Classes</h2>
            <v-container>
              <v-btn color="primary">primary</v-btn>
              <v-btn color="secondary">secondary</v-btn>
              <v-btn color="accent">accent</v-btn>
              <v-btn color="success">success</v-btn>
              <v-btn color="error">error</v-btn>
              <v-btn color="warning">warning</v-btn>
              <v-btn color="info">info</v-btn>
            </v-container>
          </v-card-actions>
        </v-form>
      </v-card-text>
    </v-card>
  </v-app>
</template>

<script>
export default {
  name: 'App',

  components: {},

  data: () => ({
    showPassword: false,
  }),
};
</script>

<script setup>
import { ref } from 'vue'

const theme = ref('light')

function onClick() {
  theme.value = theme.value === 'light' ? 'dark' : 'light'
}
</script>

<template>
  <v-responsive class="border rounded">
    <v-app :theme="theme">
      <v-app-bar class="px-3" color="green-darken-2">
        <v-spacer></v-spacer>

        <v-btn
          :prepend-icon="theme === 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'"
          text="Toggle Theme"
          slim
          @click="onClick"
        ></v-btn>
      </v-app-bar>

      <v-main>
        <v-container>
          <v-row>
            <v-col cols="12" md="6" class="mx-auto pt-16">
              <v-card
                class="mx-auto"
                prepend-icon="mdi-wrench"
                subtitle="We find ways!"
                color="green-darken-2"
              >
                <template v-slot:title>
                  <span class="font-weight-black">Login to Tri-Craft</span>
                </template>

                <v-card-text class="bg-surface-light pt-4">
                  <v-form fast-fail @submit.prevent>
                    <v-row>
                      <v-col cols="6">
                        <v-text-field label="First Name" variant="outlined"></v-text-field>
                      </v-col>
                      <v-col cols="6">
                        <v-text-field label="Last Name" variant="outlined"></v-text-field>
                      </v-col>
                    </v-row>

                    <v-text-field label="E-mail" variant="outlined"></v-text-field>

                    <v-text-field
                      label="Password"
                      type="password"
                      variant="outlined"
                    ></v-text-field>

                    <v-btn class="mt-2" type="submit" block>Submit</v-btn>
                  </v-form>

                  <v-divider class="my-5">
                    <h5 class="text-center">
                      Already have account?
                      <RouterLink class="text-success" to="/">Click here to login</RouterLink>
                    </h5>
                  </v-divider>
                </v-card-text>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </v-main>

      <v-footer color="green-darken-2" border="true" app="true"
        >2024 - Tricraft | All Rights Reserved</v-footer
      >
    </v-app>
  </v-responsive>
</template>

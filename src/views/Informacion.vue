<template>
<v-app>
  <v-row>
    <v-col>
      <v-card
        class="mx-auto text-center"
        img="https://images2.alphacoders.com/774/774364.jpg"
        dark
        max-width="900"
      >
          <v-card-text>
            <v-sheet color="rgba(0, 0, 0, .12)">
              <v-sparkline
                :value="value"
                color="rgba(255, 255, 255, .7)"
                height="70"
                padding="24"
                stroke-linecap="round"
                smooth
              >
                <template v-slot:label="item">
                  {{ item.value }}
                </template>
              </v-sparkline>
            </v-sheet>
          </v-card-text>

          <v-card-text>
            <div class="display-1 font-weight-thin">
              Horas de trabajo los ultimos días
            </div>
          </v-card-text>
          <v-card-actions>
                <v-spacer></v-spacer>
                {{ show ? 'Integrantes' : 'Integrantes' }}
                
                <v-btn
                  icon
                  @click="show = !show;"
                >
              <v-icon>{{ show ? 'mdi-chevron-up' : 'mdi-chevron-down' }}</v-icon>
            </v-btn>
            <v-spacer></v-spacer>
          </v-card-actions>
          <v-expand-transition>
            <div v-show="show">
              <v-divider></v-divider>
              <v-row>
                <v-col>
                  <v-card-text>
                  <h2>José Lillo</h2>
                    <v-spacer/>
                  <h3>Ingeniería Civil en Informática</h3>
                  </v-card-text>
                </v-col>
                <v-col>
                  <v-card-text>
                  <h2>César Rivera</h2>
                    <v-spacer/>
                  <h3>Ingeniería Civil en Informática</h3>
                  </v-card-text>
                </v-col>
              </v-row>
            </div>
          </v-expand-transition>
      </v-card>
    </v-col>
  </v-row>
</v-app>
</template>

<script>
  export default {
    name: "informacion",
    data: () => ({
      show: false,
      value: [
        3,
        9,
        5,
        5,
        2,
        8,
        10,
      ],
    }),
  }
</script>

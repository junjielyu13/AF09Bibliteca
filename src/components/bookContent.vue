<script>
export default {
  data() {
    return {
      dialogm1: '',
      dialog: false,
      date: new Date(),
      isColorChanged: false,
      originalColor: ''
    }
  },

  methods: {
    toggleColor() {
      this.isColorChanged = !this.isColorChanged
    }
  }
}
</script>

<template>
  <div class="book-detall">
    <div>
      <div style="color: gray; font-weight: 600; font-size: 14px; margin-bottom: 12px">Llibro</div>
      <div style="color: rgb(61, 82, 114); font-weight: 600; margin-bottom: 12px">
        Data and applications security XVII : status and prospects, IFIP TC11/WG11.3 Seventeenth
        Annual Working Conference on Data and Applications Security, August 4-6, 2003, Estes Park,
        Colorado, USA
      </div>
      <div style="font-size: 12px; margin-bottom: 12px">
        IFIP TC11/WG11.3 Annual Working Conference on Data and Applications Security Corporate
        Author 1st ed. 2004. Boston, Massachusetts : Kluwer Academic Publishers, [2004]
      </div>
      <div>
        <span class="mdi mdi-link"></span>
        <span style="color: rgb(71, 136, 7)"> Disponible en línia </span>
        <span class="mdi mdi-chevron-right"></span>
      </div>
    </div>

    <div style="margin-top: 20px">
      <div style="font-size: 22px; color: rgb(94, 88, 88)">Envia a</div>
      <div style="display: flex; flex-wrap: wrap; justify-content: space-around">
        <v-btn prepend-icon="mdi-printer" stacked variant="text" style="width: 120px">
          imprmir
        </v-btn>

        <v-dialog v-model="dialog" scrollable width="auto">
          <template v-slot:activator="{ props }">
            <v-btn
              prepend-icon="mdi-note-plus-outline"
              v-bind="props"
              stacked
              variant="text"
              style="width: 120px"
            >
              RESERVAR
            </v-btn>
          </template>
          <v-card>
            <v-card-title>Reservar Llibre</v-card-title>
            <v-divider></v-divider>
            <v-card-text style="height: 470px">
              <v-select
                :items="[
                  'Biblioteca de Bellas Artes',
                  'Biblioteca de Biología',
                  'Biblioteca de Ciencias de la Tierra',
                  'Biblioteca de Derecho',
                  'Biblioteca de Física y Química'
                ]"
                label="Facultat"
                variant="solo"
                required
              ></v-select>
              <VueDatePicker v-model="date" inline auto-apply position="center" />
            </v-card-text>
            <v-card-actions style="display: flex; justify-content: space-around">
              <v-btn color="red-darken-1" variant="text" @click="dialog = false"> Cancel </v-btn>
              <v-btn color="blue-darken-1" variant="text" @click="dialog = false">
                Confirmar
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-dialog>

        <v-btn
          prepend-icon="mdi mdi-heart-plus-outline"
          stacked
          variant="text"
          :class="{ changed: isColorChanged }"
          @click="toggleColor"
          style="width: 120px"
        >
          Favoritos
        </v-btn>
        <v-btn prepend-icon="mdi-share-variant-outline" stacked variant="text" style="width: 120px">
          mendeley
        </v-btn>
        <v-btn
          prepend-icon=" mdi mdi-download-box-outline"
          stacked
          variant="text"
          style="width: 120px"
        >
          Descargar
        </v-btn>
      </div>
    </div>

    <div style="margin-top: 20px">
      <div style="font-size: 22px; color: rgb(94, 88, 88)">Informació detallada</div>
      <div>
        <div style="display: flex; margin-top: 20px">
          <div style="width: 20%; font-weight: 600; color: rgb(58, 58, 58)">Autoria</div>
          <div style="width: 80%; font-size: 14px; color: rgb(90, 90, 253)">
            IFIP TC11/WG11.3 Annual Working Conference on Data and Applications Security Corporate
            Author
          </div>
        </div>
        <div style="display: flex; margin-top: 5px">
          <div style="width: 20%; font-weight: 600; color: rgb(58, 58, 58)">Títol</div>
          <div style="width: 80%; font-size: 14px; color: rgb(75, 75, 75)">
            Data and applications security XVII : status and prospects, IFIP TC11/WG11.3 Seventeenth
            Annual Working Conference on Data and Applications Security, August 4-6, 2003, Estes
            Park, Colorado, USA
          </div>
        </div>
        <div style="display: flex; margin-top: 5px">
          <div style="width: 20%; font-weight: 600; color: rgb(58, 58, 58)">Atribucions</div>
          <div style="width: 80%; font-size: 14px; color: rgb(75, 75, 75)">
            edited by Sabrina De Capitani di Vimercati, Indrakshi Ray, Indrajit Ray.
          </div>
        </div>
        <div style="display: flex">
          <div style="width: 20%; font-weight: 600; color: rgb(58, 58, 58)">Edició</div>
          <div style="width: 80%; font-size: 14px; color: rgb(75, 75, 75)">1st ed. 2004.</div>
        </div>
        <div style="display: flex; margin-top: 5px">
          <div style="width: 20%; font-weight: 600; color: rgb(58, 58, 58)">Editor</div>
          <div style="width: 80%; font-size: 14px; color: rgb(75, 75, 75)">
            Boston, Massachusetts : Kluwer Academic Publishers, [2004].
          </div>
        </div>
        <div style="display: flex; margin-top: 5px">
          <div style="width: 20%; font-weight: 600; color: rgb(58, 58, 58)">Data de creació</div>
          <div style="width: 80%; font-size: 14px; color: rgb(75, 75, 75)">[2004]</div>
        </div>
        <div style="display: flex; margin-top: 5px">
          <div style="width: 20%; font-weight: 600; color: rgb(58, 58, 58)">Descripció</div>
          <div style="width: 80%; font-size: 14px; color: rgb(75, 75, 75)">
            Security and privacy are paramount concerns in information processing systems, which are
            vital to business, government and military operations and, indeed, society itself.
            Meanwhile, the expansion of the Internet and its convergence with telecommunication
            networks are providing incredible connectivity, myriad applications and, of course, new
            threats. Data and Applications Security XVII: Status and Prospects describes original
            research results, practical experiences and innovative ideas, all focused on maintaining
            security and privacy in information processing systems and applications that pervade
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.book-detall {
  padding-top: 16px;
  margin-left: 12px;
}

.changed {
  color: red;
}
</style>

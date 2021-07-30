<template>
    <v-container>
      <br>
      <v-row
          class="float-right">
        <v-btn
            elevation="2"
            icon
        >
         <v-icon
         >
             mdi-alpha-n-circle
         </v-icon>
        </v-btn>
      </v-row>
      <v-row>
        <v-col
            sm="6" md="4" lg="3" xl="4"
            v-for="item in notes" :key="item.message">


          <v-card
              class="my-5 mx-auto pa-5"
              max-width="90%"
              outlined
              elevation="5"
          >
            <v-btn
                elevation="1"
                icon
                large
                class="float-right"
            >
              <v-icon>
                mdi-delete
              </v-icon>
            </v-btn>
            <v-list-item>
              <v-list-item-icon>
                <v-icon
                    x-large >
                  mdi-notebook-edit
                </v-icon>
              </v-list-item-icon>

              <v-list-item-content>
                <br>
                <v-list-item-title>
                  <h3>
                   başlık
                  </h3>
                </v-list-item-title>
                &emsp;
                <v-list-item-content>
                  Açıklama
                </v-list-item-content>
              </v-list-item-content>
            </v-list-item>
            <v-card-text>
              <span class=" float-right">Barış Bağcı </span><br>
              <span class=" float-right">info@yartu.com</span><br>
              <span class=" float-right">28.07.2021</span><br>

            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
</template>

<script>
export default {
  props: ['id'],
  name: "Notes",
  data: () =>({
    url : '',
    notes : [
      { message: 'Foo' },
      { message: 'Bar' }
    ],
    new_note:
        {
          "note_title": null,
          "note_description": null,
          "lesson": null,
          "teacher": null,
          "file": null,
          "file_description": null
        },
    valid : true,
    notesDNE : false, //notes data not empty
    student: localStorage.getItem('is_student'),
    dialog: false,
    snackbar: false,
    saveSnackbar: false,
    timeout: 3000,
    loading : false,
    noteRule: [
      v => !!v || 'Bu alan gereklidir.',
    ],
  }),
}
</script>

<style scoped>

</style>
<template>
  <v-main fluid>
      <v-form>
          <v-file-input label="Selecione as legendas" outlined
           append-outer-icon="mdi-send" prepend-icon="mdi-message-text"
            multiple chips v-model="files"
           @click:append-outer="processSubtitles">

          </v-file-input>
      </v-form>
      <div class="pills">
          <Pill v-for="word in groupedWords" :key="word.name"
            :name="word.name" :amount="word.amount" />
      </div>
  </v-main>
</template>

<script>
import Pill from './Pill'
export default {
    components: { Pill },
    data: function() {
        return {
            files: [],
            groupedWords: [
                { name: 'i', amount: 1234 },
                { name: 'you', amount: 900 },
                { name: 'he', amount: 853 }          
            ]
        }
    },
    methods: {
        processSubtitles() {
            console.log(this.files)
        }
    }

}
</script>

<style>
    .pills {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
    }
</style>
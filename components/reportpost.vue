<template>
  <v-tooltip bottom>
      <template v-slot:activator="{ on, attrs }">
        <v-btn icon
          v-bind="attrs"
          v-on="on"
          @click="openEmail"
        >
          <v-icon color="white">mdi-alert</v-icon>
        </v-btn>
      </template>
      <span>Report Post</span>
    </v-tooltip>
</template>

<script lang='ts'>
import { defineComponent} from '@nuxtjs/composition-api';

export default defineComponent({
  name: 'ReportPost',
  props: {
    uuid: {
      type: String,
      required: true,
    }
  },
  setup(props) {
    function openEmail() {
      window.location.href = `mailto:pubcoasters@gmail.com?subject=Report Post: ${props.uuid}`;
    }
    return { openEmail }
  }
})
</script>

<style>

</style>

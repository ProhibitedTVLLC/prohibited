<template>
    <div>
      <v-card class="mt-2">
        <!-- Title Bar -->
        <v-sheet
          tile
          color="primary"
          class="d-flex align-center justify-space-between pl-2"
        >
          <h5 class="black--text body-2">Chat Configuration</h5>

          <v-btn
            color="black"
            text
            icon
            pa-0
            @click="closeMenu"
          >
            <v-icon color="black">close</v-icon>
          </v-btn>
        </v-sheet>

        <div class="px-3 pt-3 pb-1">

          <!-- View Streamer Dashboard -->
          <v-btn
            class="d-flex mb-3"
            color="primary black--text"
            block
            small
            to="/dashboard"
          >
            Streamer Dashboard
          </v-btn>

          <!-- View Muted Users -->
          <lazy-view-muted-users-dialog />

          <!-- Modify Chat Configuration -->
          <lazy-manage-chat-config-dialog />

        </div>
      </v-card>
    </div>
</template>

<script>
  export default {
    name: 'ChatAdminMenu',

    data() {
      return {
        showMutedUsers: false,
      };
    },

    methods: {
      closeMenu () {
        this.$emit( 'close' );
      },
    },
  };
</script>

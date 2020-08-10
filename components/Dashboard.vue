<template>
  <v-row>
    <v-col cols="12" sm="8" class="py-0 d-flex">
      <v-row>
        <v-col
          v-for="card in cards"
          :key="card.title"
          :cols="card.flex"
          class="d-flex"
        >
          <v-card flat class="shadow ma-1">
            <v-card-title>
              {{ card.title }}
              <v-spacer />
              <v-card-actions>
                <v-btn icon>
                  <v-icon x-large color="primary">{{ arrow }}</v-icon>
                </v-btn>
              </v-card-actions>
            </v-card-title>
            <v-card-text> {{ card.text }}</v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-col>
    <v-col cols="12" sm="4">
      <v-form>
        <h2>Buat Pengumuman</h2>
        <p>Link</p>
        <v-text-field solo label="Sisipkan link lampiran"></v-text-field>
        <p>Pengumuman</p>
        <v-textarea
          solo
          label="Sampaikan apa yang ingin kamu umumkan pada peserta lomba"
          auto-grow
        ></v-textarea>
        <v-btn class="primary d-flex" rounded-sm depressed width="100%"
          >Kirim Pengumuman</v-btn
        >
      </v-form>
      <v-card flat class="shadow mt-6">
        <v-container class="d-flex">
          <h3>Ganti Link</h3>
          <p>Ganti link pada tombol web peserta</p>
          <v-card-actions>
            <v-btn icon>
              <v-icon x-large color="warning">{{ arrow }}</v-icon>
            </v-btn>
          </v-card-actions></v-container
        >
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      link: '',
      cards: [
        {
          title: 'Lihat Karya LKTIN',
          text: 'Lihat karya yang sudah diunggah peserta lomba LKTIN',
          flex: 6,
        },
        {
          title: 'Lihat Karya Microteaching',
          text: 'Lihat karya yang sudah diunggah peserta lomba Microteaching',
          flex: 6,
        },
        {
          title: 'Lihat Konfirmasi',
          text: 'Lihat bukti pembayaran yang sudah dikirim oleh peserta',
          flex: 6,
        },
        {
          title: 'Lihat Pendaftar',
          text:
            'Lihat dan kendalikan siapa saja yang sudah mendaftar di tiap lomba',
          flex: 6,
        },
      ],
      arrow: 'mdi-arrow-right-circle',
    }
  },
}
</script>

<style scoped>
.v-input__slot {
  border: 3px solid red !important;
}
.shadow {
  box-shadow: 0 2px 6px 0 rgba(0, 0, 0, 0.2) !important;
  border-radius: 16px !important;
}
</style>

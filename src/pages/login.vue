<template>
  <q-page class="bg-grey-3">
      <div class="row">
          <q-card class="fixed-center col-md-4 col-xs-12 bg-white">
              <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md"
      >
    <q-input
        filled
        v-model="name"
        label="Masukan nama anda *"
        hint="Nama lengkap"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
      />

    <q-input
        filled
        type="password"
        v-model="pass"
        label="Masukan Password *"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
      />
    <div>
      <q-btn label="Submit" type="submit" color="primary"/>
      <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
    </div>
    </q-form>
          </q-card>
      </div>
  </q-page>
</template>
<script>
export default {
  data () {
    return {
      name: null,
      pass: null
    }
  },
  methods: {
    onSubmit () {
      if (this.name === 'anu' && this.pass === '18425009') {
        this.$q.notify({
          type: 'positive',
          message: 'Selamat Berhasil Login'
        })
        this.$router.push('/home')
      } else {
        this.$q.notify({
          type: 'negative',
          message: 'gagal login username/password salah'
        })
      }
    },
    onReset () {
      console.log('ini tombol reset')
    }
  }
}
</script>

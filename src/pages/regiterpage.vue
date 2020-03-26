<template>
  <q-page>
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
    <div>Masukan Jenis Kelamin</div>
      <div>
    <div>
      <q-radio v-model="shape" val="Jantan" label="Jantan" />
      <q-radio v-model="shape" val="Betina" label="Betina" />
    </div>

    <div class="q-px-sm">
      Your selection is: <strong>{{ shape }}</strong>
    </div>
  </div>
      <q-input
        filled
        v-model="email"
        label="Masukan email anda *"
        hint="example@gmail.com"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
      />

    <q-input
        filled
        v-model="lahir"
        label="Masukan tanggal lahir anda *"
        hint="tanggal-bulan-tahun"
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

    <q-input
        filled
        type="password"
        v-model="passre"
        label="Ketik Ulang password *"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Please type something']"
      />
      <q-img
          src="https://placeimg.com/500/300/nature"
          :ratio="16/9"
        />
    <div>
      <q-btn to="/" label="Submit" type="Submit" color="primary"/>
      <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
    </div>
    </q-form>
  </q-page>
</template>
<script>
export default {
  data () {
    return {
      name: null,
      pass: null,
      passre: null,
      email: null,
      lahir: null,
      shape: null
    }
  },
  onSubmit () {
    console.log('ini tombol submit')
  },
  onReset () {
    console.log('ini tombol reset')
  }
}
</script>

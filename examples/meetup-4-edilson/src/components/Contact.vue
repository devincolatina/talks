<template>
  <div>
    <div v-show="isLoading">Buscando...</div>
    <form>
      <label for="cep">CEP
        <input type="number" id="cep" v-model="cep" v-on:input="getAddressByCep">
      </label> <br>
      <label for="logradouro">Logradouro
        <input id="logradouro" v-model="logradouro" disabled>
      </label> <br>
      <label for="bairro">Bairro
        <input id="bairro" v-model="bairro" disabled>
      </label> <br>
      <label for="cidade">Cidade
        <input id="cidade" v-model="cidade" disabled>
      </label> <br>
      <label for="uf">Estado
        <input id="uf" v-model="uf" disabled>
      </label> <br>
    </form>
  </div>
</template>

<script>
export default {
  data () {
    return {
      cep: '',
      logradouro: '',
      bairro: '',
      cidade: '',
      uf: '',
      isLoading: false
    }
  },

  methods: {
    getAddressByCep () {
      if (this.cep.length < 8) return
      this.isLoading = true

      setTimeout(() => {

        fetch(`https://viacep.com.br/ws/${this.cep}/json/`)
          .then(response => {
            return response.json()
          })
          .then(data => {
            this.logradouro = data.logradouro
            this.bairro = data.bairro
            this.cidade = data.localidade
            this.uf = data.uf
          })
          .finally(() => {
            this.isLoading = false
          })

      }, 1000)
    }
  }
}
</script>

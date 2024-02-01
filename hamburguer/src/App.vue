<template>
  <div id="app">
    <header>
      <nav class="nav nav-pills nav-fill">
        <a class="nav-link" aria-current="page">Monte seu lanche</a>
      </nav>
    </header>
    <div class="container">
      <div id="imagens">
        <div class="col mt-5">
          <div class="row">
            <div class="col imagens">
              <!-- <img :src="pao([0])" > -->
              <img :src="pao[0]" >
              <img :src="alface" >
              <img :src="ketchup" >
              <img :src="maionese" >
              <img :src="mostarda" >
              <img :src="hamburguer" >
              <img :src="pao[1]" >
              <!-- <img :src="pao([1])" > -->

            </div>
          </div>
        </div>
      </div>

      <div id="cardes">
        <div class="col">
          <div class="row">
            <div class="card" style="width: 18rem;">
              <div class="card-header">TIPO DO PÃO</div>
              <div class="card-body">
                <div class="form-check form-check-inline">
                  <input class="form-check-input" type="radio" value="gergelim" v-model="inputPao">
                  <label class="form-check-label" >Gergelim</label>
                </div>
                <div class="form-check form-check-inline">
                  <input class="form-check-input" type="radio" value="australiano" v-model="inputPao">
                  <label class="form-check-label" >Australiano</label>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="col">
          <div class="row">
            <div class="card" style="width: 18rem;">
              <div class="card-header">SALADAS</div>
              <div class="card-body">
                <div class="form-check">
                  <input class="form-check-input" type="checkbox" value="alface" v-model="inputSalada">
                  <label class="form-check-label">Alface</label>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="col">
          <div class="row">
            <div class="card" style="width: 18rem;">
              <div class="card-header">MOLHOS</div>
              <div class="card-body">
                <div class="form-check form-check-inline ">
                  <input class="form-check-input " type="checkbox" value="ketchup" v-model="inputMolhos">
                  <label class="form-check-label">Ketchup</label>
                </div>
                <div class="form-check form-check-inline">
                  <input class="form-check-input" type="checkbox" value="mostarda" v-model="inputMolhos">
                  <label class="form-check-label">Mostarda</label>
                </div>
                <div class="form-check form-check-inline">
                  <input class="form-check-input" type="checkbox" value="maionese" v-model="inputMolhos">
                  <label class="form-check-label">Maionese</label>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="col">
          <div class="row">
            <div class="card" style="width: 18rem;">
              <div class="card-header">TIPO DO HAMBURGUER</div>
              <div class="card-body">
                <div class="card-body">
                <div class="form-check form-check-inline ">
                  <input class="form-check-input" type="radio" value="bovino" v-model="inputHamburguer">
                  <label class="form-check-label">Bovino</label>
                </div>
                <div class="form-check form-check-inline">
                  <input class="form-check-input" type="radio" value="frango" v-model="inputHamburguer">
                  <label class="form-check-label">Frango</label>
                </div>
                <div class="">
                <div class="form-check form-check-inline">
                  <input class="form-check-input" type="radio" value="soja" v-model="inputHamburguer">
                  <label class="form-check-label">Soja</label>
                </div>
              </div>
              </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',

  data() {
    return {
      inputPao: '',
      inputSalada: [],
      inputMolhos: [],
      inputHamburguer: ''
    }
  },
  computed: {
    pao() {
      switch(this.inputPao) {
        case 'gergelim' :
          return ['imagens/pao_gergelim_superior.png', 'imagens/pao_gergelim_inferior.png']

        case 'australiano' : 
          return ['imagens/pao_australiano_superior.png', 'imagens/pao_australiano_inferior.png']

        default:
          return ['imagens/padrao/pao_superior.png', 'imagens/padrao/pao_inferior.png']
      }
    },
    alface() {
      if (this.inputSalada.includes('alface')) {
        return 'imagens/alface.png'
      }
      return 'imagens/padrao/alface.png'
    },
    ketchup() {
      if (this.inputMolhos.includes('ketchup')) {
        return 'imagens/ketchup.png'
      }
      return 'imagens/padrao/molho.png'
    },
    maionese() {
      if (this.inputMolhos.includes('maionese')) {
        return 'imagens/maionese.png'
      }
      return 'imagens/padrao/molho.png'

    },
    mostarda() {
      if (this.inputMolhos.includes('mostarda')) {
        return 'imagens/mostarda.png'
      }
      return 'imagens/padrao/molho.png'

    },
    hamburguer() {
      switch(this.inputHamburguer) {
        case 'bovino': 
          return 'imagens/bovino.png'

        case 'frango':
          return 'imagens/frango.png'

        case 'soja':
          return 'imagens/soja.png'

        default: 
          return 'imagens/padrao/hamburguer.png'

      } 

    }
  }

}
</script>

<style scoped>

  .nav {
    background: rgb(112, 112, 112);
  }
  .container { 
    display: flex;
    justify-content: space-around;

  }
  .card {
    margin-top: 2rem;
  }
  .imagens {
    display: flex;
    flex-direction: column;
  }
</style>

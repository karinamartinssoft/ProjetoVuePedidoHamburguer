<template>
    <div>
      <p>Componente de Mensagem</p>
       <div> 
        <form id="burguer-form">
            <div class="input-container">
                <label for="nome">Nome do Cliente</label>
                <input type="text" id="nome" name="name" v-model="nome" placeholder="Digite o seu nome">
            </div>
            <div class="input-container">
              <label for="pao">Escolha o pão:</label>
              <select name="pao" id="pao" v-model="pao">
                <option value="">Selecione o seu pão</option>
                <option value="integral">Integral</option>
              </select>
            </div>
            <div class="input-container">
              <label for="carne">Escolha a carne do seu Burguer:</label>
              <select name="carne" id="carne" v-model="carne">
                <option value="">Selecione o seu tipo de carne</option>
                <option value="marminha">Maminha</option>
              </select>
            </div>
            <div class="input-container">
              <label id="opcionais-title" for="opcionais">Selecione os opcionais:</label>
              <div class="checkbox-container">
                <input type="checkbox" name="opcionais" v-model="opcionais" value="salame">
                <span>Salame</span>
              </div>  
              <div class="checkbox-container">
                <input type="checkbox" name="opcionais" v-model="opcionais" value="salame">
                <span>Salame</span>
              </div> 
              <div class="checkbox-container">
                <input type="checkbox" name="opcionais" v-model="opcionais" value="salame">
                <span>Salame</span>
              </div> 
              <div class="checkbox-container">
                <input type="checkbox" name="opcionais" v-model="opcionais" value="salame">
                <span>Salame</span>
              </div>           
            </div>
            <div class="input-container">
                <input type="submit" class="submit-btn" value="Criar meu Burguer!">
            </div>
        </form>
       </div>
   </div>
</template>

<script>
export default {
    name:"BurguerForm",
    data(){
        return{
         paes: null,
         carnes: null,
         opcionaisdata: null,
         nome: null,
         pao: null,
         carne: null,
         opcionais: [],
         status: "Solicitado",
         msg: null
        }
    },
    methods: {
        async getIngredientes() {
            const req = await fetch("http://localhost:3000/ingredientes");

        }

    }

    
}
</script>

<style scoped>
#burguer-form{
    max-width: 400px;
    margin: 0 auto;
}

.input-container{
    display: flex;
    flex-direction: column;
    margin-bottom: 20px;
}
label{
    font-weight: bold;
    margin-bottom: 15px;
    color: #222;
    padding: 5px 10px;
    border-left: 4px solid #FCBA03;
}

input, select{
  padding: 5px 10px;
  width: 300px;
}

#opcionais-container{
    flex-direction: row;
    flex-wrap: wrap;

}

#opcionais-title{
    width: 100%;
}

.checkbox-container{
    display: flex;
    align-items: flex-start;
    width: 50%;
    margin-bottom: 20px;
}

.checkbox-container span,
.checkbox-container input{
    width: auto;

}

.checkbox-container span{
    margin-left: 6px;
    font-weight: bold;
}

.submit-btn{
    background-color: #222;
    color: #FCBA03;
    font-weight: bold;
    border: 2px solid #222;
    padding: 10px;
    font-size: 16px;
    margin: 0 auto;
    cursor: pointer;
    transition: .5s;

}

.submit-btn:hover{
    background-color: transparent;
    color: #222
}

</style>
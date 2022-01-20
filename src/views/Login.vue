<template>
  <v-container fill-height fluid text-center>
    <v-container>
      <v-row>
        <v-col
          class="black--text text-center mx-auto pb-5"
          cols="2"
          sm="5"
          offset="5"
        >
          <h1 class="h1">Faça seu Login</h1></v-col
        >
      </v-row>
      <v-row class="elavation-3 mx-auto">
        <v-col cols="auto">
          <v-img
            max-height="200"
            max-width="300"
            src="@/assets/images/logogrande.png"
          >
          </v-img>
        </v-col>
        <v-col>
          <v-form>
            <v-text-field label="Email" v-model="user.email"></v-text-field>
            <v-text-field
              label="Senha"
              v-model="user.password"
              :type="show ? 'text' : 'password'"
              :append-icon="show ? 'mdi-eye' : 'mdi-eye-off'"
              @click:append="show = !show"
            ></v-text-field>
            <v-btn color="green" @click="login"> Login</v-btn>
            <v-btn class="ml-4" color="red" @click="reset">
              Cancelar</v-btn
            >
          </v-form>
        </v-col>
      </v-row>
    </v-container>
    <v-snackbar color="red" v-model="errorLogin" danger multline timeout="2050">
      Credenciais incorretas
    </v-snackbar>

    <v-dialog v-model="novaConta" persistent max-width="300">
      <v-card>
        <v-card-tittle>Conta não encontrada.</v-card-tittle>
        <v-card-text>
          Não há nenhuma conta com as informações apresentadas. Gostaria de criar uma nova ?
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="green darken-2" text @click="criarNovaConta">Sim</v-btn>
          <v-btn color="red darken-2" text @click="novaConta = false">
            Não</v-btn
          >
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-container>
</template>

<script>

</script>

<style scoped>
</style> 
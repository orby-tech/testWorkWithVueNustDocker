
<template>
  <v-app id="inspire">
    <v-main>
      <v-container
        fluid>
            <v-row justify="center">
                <v-card>    
                    <v-card-title>Привет, {{username}}</v-card-title>
                <v-avatar color="indigo" width=250 height=250>
                    <img
                        class="profile__img"
                        :src="imgAdress"
                        alt="profile IMG"
                        > 
                </v-avatar  > 
                
                <v-card-subtitle>Ваш e-mail: {{email}}</v-card-subtitle> 

                </v-card>
            </v-row>
                
      </v-container>
    </v-main>
  </v-app>
</template>


<script>
export default {
    name:"loginForm",
    props: ['username'],
    data: function () {
        return {
        login: "",
        password: "",
        email: "",
        imgAdress:"",
        }
    },
    mounted() {
        this.loadingData()
    },
    methods: {
        avtorization () {
            setTimeout(()=>{
                this.$emit('login', this.login)
            }, 300)
        },
        loadingData(){
            setTimeout(()=>{
                this.email = this.username + "." + this.username + "ich@mail.com"
                this.imgAdress = "https://www.publicdomainpictures.net/pictures/290000/nahled/kitty-cat-1550713752BKA.jpg"
            }, 300)
        }
    }
}
</script>

<style lang="scss">
    .profile__img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }
</style>

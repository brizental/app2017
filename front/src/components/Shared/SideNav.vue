<template>
    <ul id="slide-out" class="side-nav">
        <li>
            <div class="userView grey lighten-2">
                <p class="userinfo grey-text text-darken-3">{{useremail}}</p>
                <button v-on:click="logout()" class="waves-effect waves-light btn-flat grey lighten-1 grey-text text-darken-4">SAIR</button>
            </div>
        </li>
        <li><router-link to="/news"><i class="material-icons">info_outline</i>Notícias & Informes</router-link></li>
        <li><router-link to="/program"><i class="material-icons">today</i>Grade de Atividades</router-link></li>
        <li><router-link to="/favs"><i class="material-icons">star</i>Favoritos</router-link></li>
        <li><router-link to="/maps"><i class="material-icons">map</i>Mapa do Alojamento</router-link></li>
        <li><router-link to="/faq"><i class="material-icons">help_outline</i>Perguntas Frequentes</router-link></li>
        <li><router-link to="/phones"><i class="material-icons">call</i>Telefones Importantes</router-link></li>
    </ul>
</template>


<script>
export default {
    name: 'sidenav',
    methods: {
        logout: function() {
            this.$store.dispatch('logout');
        }
    },
    computed: {
        username() {
            return this.$store.state.username
        },
        useremail() {
            return this.$store.state.useremail
        }
    }
}
</script>


<style scoped lang="scss">

    p.userinfo {
        line-height: 25px;
        padding-bottom: 5px;
        margin-top: 0;
        margin-bottom: 0;

        strong {
            font-weight: 600;
        }
    }
    
    .btn-flat {
        min-width: auto;
        margin-bottom: 15px;
    }

    .side-nav li>a.router-link-active {
        font-weight: 700;
    }
</style>

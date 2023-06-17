<template>
 <nav class="navbar">
    <img class="hamburguesa" src="../assets/icons/hamburgermenu.png" alt="menu-hamburguesa">
    <img class="logo" src="../assets/icons/logo.png" alt="logo">
    <div class="input-container">
        <img class="cursor" src="../assets/icons/cursor.png" alt="cursor">
        <input class="input" type="text" placeholder="Search here">
        <img class="lupa" src="../assets/icons/lupa.png" alt="lupa">
    </div>
    <button class="btn"><img src="../assets/icons/tuerca.png" alt="tuerca"></button>
   
    <div class="icon-container">
        <img class="icon-navbar" src="../assets/icons/notification.png" alt="notificacion">
        <img class="icon-navbar chat" src="../assets/icons/chat.png" alt="chat">
        <img class="icon-navbar promos" src="../assets/icons/promos.png" alt="promos">
    </div>
    <div class="user-container">
        <!-- <img class="user-logo" src="../assets/icons/placeholder.png" alt="user-logo"> -->
        <button class="btn-user-logo" ><img class="user-logo" src="../assets/icons/user.png" alt="user-logo"> </button>
        <p class="user-name">David</p>
        <img src="../assets/icons/triangulo.png" alt="ícono del dropdown">
    </div>
 
 </nav>
</template>

<script>
export default {

}
</script>

<style scoped>
/* Estilos para el menú Hamburguesa y el logo */
.navbar{
    align-items: center;
    display:flex;
    margin-top:20px;
    padding-left:20px ;
    padding-right:10px ;
    width:96%;
    /* border:1px solid white; */
}
.hamburguesa{
    width:40px;
}
.logo{
    width: 70px;
}
/* Estilos para el input */
.input-container{
    height: 45px;
    margin-left: 7%;
    position:relative;
    width: 55%;
    /* display:none; */
    
    
}
.input-container .lupa{
    position:absolute;
    right: 8%;
    top:10px;
    z-index: 2;
}
.input-container .input{
    background-color: rgb(28,33,38);
    border-radius: 10px;
    border:none;
    color:rgb(185,185,185);
    padding: 15px 0;
    padding-left:25px;
    position: absolute;
    width: 90%;
    z-index: 1;
}

.input-container .input::placeholder{
    color:rgb(185,185,185);
}
.input-container .cursor{
    position: absolute;
    z-index:2;
    left: 18px;
    top:10px;
}

/* Estilos para el botón de ajustes */
.btn{
    background-color: rgb(19,180,151);
    border-radius: 10px;
    border:none;
    padding: 8px;
  
}
.btn img{
    width: 25px;
}

/* Estilos para los íconos de notificaciones */
.icon-container{
    align-items: center;
    display: flex;
    gap: 10px;
    margin-left: 20%;
    padding-right: 30px;
    border-right:2px solid rgb(42,47,52);
    /* border:1px solid yellow; */
}
.icon-navbar{
    width: 50px;
}

/* Estilos para los datos del perfil del usuario  -> Desde aquí no he refactorizado */
.user-container{
    display:flex;
    align-items: center;
    gap:15px;
    margin-left: 35px;
    padding-right: 20px;
    border-radius: 10px;
    border:2px solid rgb(42,47,52);
    /* border:1px solid pink; */
}
.btn-user-logo{
    background-color: rgb(196,196,196);
    padding: 10px;
    border-radius: 10px;
    border:none;
}
.user-container .user-logo{
    width: 25px;
    height: 25px;
    visibility: hidden;
}
.user-container .user-name{
    color:rgb(228,228,229);
    font-size: 12px;
}

/* Para dispositivos de pantalla muy grande*/
@media(min-width:1700px){
    .navbar{
        
        padding-left:40px ;
        padding-right:0px ;
        width:96%;
    }
    .btn{
        margin-left: -2%;
    }
}

/* Para Tablets */
@media(max-width:950px){
    .navbar{
        padding-left:0 ;
        padding-right:0 ;
        width:96%;
        margin-left:auto;
        margin-right: auto;
    }
    .input-container,.btn,.chat,.promos,.user-name{
        display:none;
    }
    .user-container .user-logo{
        visibility:visible;
    }
    .icon-container{
        margin-left: 65%;
        margin-right: 2%;
        padding-right: 0;
        border-right:none;
    }
    .icon-navbar{
        width: 40px;
    }
    .user-container{
        margin-left: 0;
        padding-right: 10px;
        gap:10px;
    }
    .btn-user-logo{
        padding: 10px;
        border-radius: 10px;
    }
    .user-container .user-logo{
        width: 20px;
        height: 20px;
    }
}

/* Para dispositivos móviles */
@media(max-width:450px){
    .hamburguesa{
        width:35px;
    }
    .logo{
        width: 55px;
    }
    .icon-container{
        margin-left: 40%;
    }
}
</style>
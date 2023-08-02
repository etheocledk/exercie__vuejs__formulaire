<template>
    <div class="wrapper">
        <div class="container">
            <div class="header__color">
                <div>
                    <svg xmlns="http://www.w3.org/2000/svg" height="1em"
                        viewBox="0 0 576 512"><!--! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
                        <path
                            d="M0 24C0 10.7 10.7 0 24 0H69.5c22 0 41.5 12.8 50.6 32h411c26.3 0 45.5 25 38.6 50.4l-41 152.3c-8.5 31.4-37 53.3-69.5 53.3H170.7l5.4 28.5c2.2 11.3 12.1 19.5 23.6 19.5H488c13.3 0 24 10.7 24 24s-10.7 24-24 24H199.7c-34.6 0-64.3-24.6-70.7-58.5L77.4 54.5c-.7-3.8-4-6.5-7.9-6.5H24C10.7 48 0 37.3 0 24zM128 464a48 48 0 1 1 96 0 48 48 0 1 1 -96 0zm336-48a48 48 0 1 1 0 96 48 48 0 1 1 0-96z" />
                    </svg>
                </div>
                <p class="price">Total à payer</p>
                <h1>12000 <span>Fcfa</span></h1>
            </div>
            <div class="account__div">
                <p>Sélectionner un mode de paiement</p>
                <div class="count">
                    <div @click="paymentMethod = 'mobile'">
                        <div>
                            <svg xmlns="http://www.w3.org/2000/svg" height="1em"
                                viewBox="0 0 384 512"><!--! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
                                <path
                                    d="M80 0C44.7 0 16 28.7 16 64V448c0 35.3 28.7 64 64 64H304c35.3 0 64-28.7 64-64V64c0-35.3-28.7-64-64-64H80zm80 432h64c8.8 0 16 7.2 16 16s-7.2 16-16 16H160c-8.8 0-16-7.2-16-16s7.2-16 16-16z" />
                            </svg>
                        </div>
                        <p>Paiement mobile</p>
                    </div>
                    <div @:click="paymentMethod = 'carte'">
                        <div>
                            <svg xmlns="http://www.w3.org/2000/svg" height="1em"
                                viewBox="0 0 576 512"><!--! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
                                <path
                                    d="M64 32C28.7 32 0 60.7 0 96v32H576V96c0-35.3-28.7-64-64-64H64zM576 224H0V416c0 35.3 28.7 64 64 64H512c35.3 0 64-28.7 64-64V224zM112 352h64c8.8 0 16 7.2 16 16s-7.2 16-16 16H112c-8.8 0-16-7.2-16-16s7.2-16 16-16zm112 16c0-8.8 7.2-16 16-16H368c8.8 0 16 7.2 16 16s-7.2 16-16 16H240c-8.8 0-16-7.2-16-16z" />
                            </svg>
                        </div>
                        <p>Carte de crédit</p>
                    </div>
                </div>
            </div>
            <div class="formulaire" v-if="paymentMethod === 'mobile'">
                <div>
                    <div>
                        <label for="name">Nom et Prénoms</label>
                        <div class="input">
                            <input type="text">
                        </div>
                    </div>


                    <div>
                        <label for="name">Numéro de téléphone</label>
                        <div class="input">
                            <input type="text">
                        </div>
                    </div>
                </div>
            </div>
                <div class="fermeture" v-else-if="paymentMethod === 'carte'">
                    <h1>Fermeture</h1>
                </div>
                <button>Payer 12000Fcfa</button>
                <p>Paiement sécurisé fournit par <a href="#">kkiapay</a></p>
            
        </div>
    </div>
</template>
<script lang="ts" setup>
import { ref } from 'vue'
const paymentMethod = ref('mobile');



</script>
<style scoped>
.wrapper {
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.header__color {
    background: linear-gradient(rgb(251, 49, 49), rgb(179, 50, 65));
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 20px 0;
    color: white;
}

.header__color div {
    background-color: white;
    border-radius: 50%;
    width: 50px;
    height: 50px;
    display: flex;
    align-items: center;
    justify-content: center;
}

p.price {
    margin-bottom: -5px;
}



.container {
    width: 400px;
    box-shadow: 5px 5px 5px 5px rgba(0, 0, 0, 0.074);
}

.account__div {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    font-size: 15px;
    gap: 10px;
    background-color: rgba(248, 214, 214, 0.442);
}

.count {
    display: flex;
    gap: 40px;
}

.count div {
    text-align: center;
}

.formulaire {
    background-color: white;
    padding: 10px 25px;
}

.input {
    width: 350px;
    height: 30px;
    margin-bottom: 25px;
}

input {
    width: 100%;
    height: 100%;
    border-color: rgba(0, 0, 0, 0.353);
    border-radius: 3px;
    margin-top: 5px;
}

button {
    width: 100%;
    padding: 10px 0;
    border: none;
    background-color: red;
    color: white;
    font-size: 16px;
    font-weight: bold;
    margin-bottom: 40px;
}

.formulaire p {
    text-align: center;
}

a {
    text-decoration: none;
    font-size: 15px;
}

.count div div {
    background-color: white;
    padding: 15px 30px;
    border: 2px solid red;
    border-radius: 3px;
    margin-bottom: -5px;
}

.count div p {
    font-size: 14px;
}
</style>
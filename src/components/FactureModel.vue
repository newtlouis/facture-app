<template>
    <div @click="checkClick" class="facture">
        <form @submit.prevent="sendFacture">
            <h1>Nouvelle Facture:</h1>
            <div class="from">
                <h3>Facture de:</h3>
                <div class="input">
                    <label for="billerAdress">Adresse</label>
                    <input id="billerAdress" v-model="billerAdress" required type="text">
                </div>
                <div class="locationDetail">
                    <div class="input">
                    <label for="billerCity">Ville</label>
                    <input id="billerCity" v-model="billerCity" required type="text">
                </div>
                <div class="input">
                    <label for="billerCP">Code Postal</label>
                    <input id="billerCP" v-model="billerCP" required type="text">
                </div>
                <div class="input">
                    <label for="billerCountry">Pays</label>
                    <input id="billerCountry" v-model="billerCountry" required type="text">
                </div>
                </div>
            </div>
        </form>
        facture
    </div>
</template>

<script>
export default {
    name:"factureModel",
    data(){
        return{
            billerAdress: null,
            billerCity: null,
            billerCP: null,
            billerCountry: null,
            clientName: null,
            clientEmail: null,
            clientAdress: null,
            clientCity: null,
            clientCP: null,
            clientCountry: null,
            factureDate: null,
            facturePending: null,
            factureDraft: null,
            factureList: [],
            factureTotal: 0,
            paymentDueDate: null,
            productDescription: null,


        }
    }

}
</script>
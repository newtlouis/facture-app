<template>
    <div @click="checkClick" class="facture">
        <form @submit.prevent="sendFacture">
            <h1>Nouvelle Facture:</h1>
            <!-- FROM -->
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
            <!-- TO -->
            <div class="to">
                <h3>Destinataire</h3>
                <div class="input">
                    <label for="clientName">Name</label>
                    <input id="clientName" v-model="clientName" required type="text">
                </div>
                <div class="input">
                    <label for="clientAdress">Adresse</label>
                    <input id="clientAdress" v-model="clientAdress" required type="text">
                </div>
                <div class="input">
                    <label for="clientEmail">Email</label>
                    <input id="clientEmail" v-model="clientEmail" required type="text">
                </div>

                <div class="locationDetail">
                    <div class="input">
                        <label for="clientCity">Ville</label>
                        <input id="clientCity" v-model="clientCity" required type="text">
                    </div>
                    <div class="input">
                         <label for="clientCP">Code Postal</label>
                        <input id="clientCP" v-model="clientCP" required type="text">
                    </div>
                    <div class="input">
                         <label for="clientCountry">Pays</label>
                         <input id="clientCountry" v-model="clientCountry" required type="text">
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
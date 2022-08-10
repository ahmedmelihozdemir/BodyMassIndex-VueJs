<template>
    <div class="container">
        <h1>Body Mass Index Calculate</h1>
        <div class="row">
            <div class="input-box col-md-6">
                <label for="">
                    Kütlenizi giriniz. (Kg)
                <input
                    class="input-box-input"
                    type="number"
                    placeholder="Kütlenizi giriniz."
                    v-model="bodyKg"
                />
                </label>
                <label for="">
                    Boyunuzu giriniz. (Cm)
                <input
                    class="input-box-input"
                    type="number"
                    placeholder="Boyunuzu giriniz."
                    v-model="bodyCm"
                />
                </label>
                <hr />
            </div>
        </div>
        <button class="btn btn-primary" @click="calculate">Hesapla</button>
    </div>
</template>

<script>
import { useRouter, useRoute } from 'vue-router'
import { ref } from "vue";

export default {
    setup() {
        const router = useRouter();
        const route = useRoute();


        const bodyKg = ref(null);
        const bodyCm = ref(null);
        const bodyMass = ref(null);

        const calculate = ref(() => {
            bodyMass.value = bodyKg.value / (bodyCm.value / 100) ** 2;
            console.log(bodyMass.value.toFixed(2));
            router.push({
                name: 'about',
                params: {
                    bodyMass: bodyMass.value.toFixed(2),
                },
            });
            return bodyMass;
        });

        return {
            bodyKg,
            bodyCm,
            bodyMass,
            calculate,
        };
    },
};
</script>

<style lang="scss">
h1,h3{
    margin: 15px auto;
    text-align: center;
    color: rgba(20, 117, 117, 0.637);
    text-shadow: 1px 1px 1px rgb(56, 54, 54), 0 0 25px rgb(47, 47, 184),
        0 0 3px rgba(43, 43, 147, 0.781);
}
.input-box {
    padding: 10px;
    margin: 2px auto;
    
    .input-box-input{
        margin: 5px;
        width: 80%;
        height: 30px;
        border-radius: 5px;
        border: 1px solid rgba(116, 19, 185, 0.776);
        background-color: rgba(12, 109, 109, 0.299);
        &:hover {
            background-color: rgba(12, 109, 109, 0.5);
            cursor: pointer;
            box-shadow: 1px 1px 10px rgba(112, 13, 199, 0.5);
        }
    }
}
.btn {
    height: 40px;
    width: 100px;
    background-color: rgba(20, 117, 117, 0.734);
    border: none;
    border-radius: 10px;
    &:hover{
        background-color: rgba(20, 117, 117, 0.637);
        cursor: pointer;
        box-shadow: 1px 1px 1px rgb(56, 54, 54), 0 0 25px rgb(47, 47, 184),
        0 0 3px rgba(43, 43, 147, 0.781);
        
    }
}
</style>

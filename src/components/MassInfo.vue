<template>
    <div class="container">
        <div class="row">
            <h3>Your index {{ $route.params.bodyMass }}</h3>
        </div>

        <div class="row">
            <div
                class="body-mass-info col-md-2"
                :class="{
                    'body-mass-info-red':
                        $route.params.bodyMass > 0 &&
                        $route.params.bodyMass <= 18.4,
                }"
            >
                <h2>İdeal Kilonun Altındasın</h2>
            </div>
            <div
                class="body-mass-info col-md-2"
                :class="{
                    'body-mass-info-red':
                        $route.params.bodyMass > 18.5 &&
                        $route.params.bodyMass <= 24.99,
                }"
            >
                <h2>İdeal Kilodasın</h2>
            </div>
            <div
                class="body-mass-info col-md-2"
                :class="{
                    'body-mass-info-red':
                        $route.params.bodyMass > 25 &&
                        $route.params.bodyMass <= 29.99,
                }"
            >
                <h2>İdeal Kilonun Üstündesin</h2>
            </div>
            <div
                class="body-mass-info col-md-2"
                :class="{
                    'body-mass-info-red':
                        $route.params.bodyMass > 30 &&
                        $route.params.bodyMass <= 34.99,
                }"
            >
                <h2>İdeal Kilonun Çok Üstündesin - Obez</h2>
            </div>
            <div
                class="body-mass-info col-md-2"
                :class="{ 'body-mass-info-red': $route.params.bodyMass > 35 }"
            >
                <h2>İdeal Kilonun Çok Üstündesin - Morbid Obez</h2>
            </div>
        </div>
        <hr>
        <div class="row">
            <div class="info-obez col-md-6">
                <h2>Vücut Kitle İndeksi Sonuçları Ne Anlama Gelir?</h2>
                <p>
                    Vücut kitle indeksi hesaplamasında yağ oranı, vücut tipi,
                    yağ ve kas dokusu gibi etmenler yer almaz. Bu nedenle,
                    uzmanlar ideal kilo hesaplamada beden kitle indeksi ve bel
                    çevresinin ölçümü dışında, metabolizma hızı ölçümü ve
                    detaylı vücut analizleriyle de kişinin eğer kilo sorunu
                    hakkında daha ayrıntılı bilgi elde ederler. Kişinin ideal
                    kilosunun altında ya da üstünde olması; diğer etmenlerle
                    birlikte hekim tarafından değerlendirilmelidir. Mevcut
                    sağlık sorunlarını gidermek ve olası sağlık sorunlarını
                    önlemek için hekimle birlikte hareket edilmelidir.
                    Erkeklerde bel çevresi 94 cm’yi geçerse artmış risk, 102
                    cm’yi geçerse yüksek risk olarak görülür. Bu oran kadınlarda
                    ise 80 cm’yi geçerse artmış risk, 88 cm’yi geçerse yüksek
                    risk olarak kabul edilir.
                </p>
            </div>
            <div class="info-obez col-md-6">
                <h2>Detaylı Vücut Kitle İndeksi ile Obezite Hesaplama</h2>
                <p>
                    Detaylı vücut kitle indeksi ile obezite hesaplamada yaşı ve
                    cinsiyet de dikkate alınarak kilonun, vücut yağ yüzdesinin
                    ve bel çevre ölçüsünün normal değerlerde olup olmadığını
                    öğrenilebilir. Öncelikle yağ dokusunun vücudun neresinde
                    toplandığını bilmek, obezitenin tanı ve tedavisi için
                    oldukça önemlidir. Yağ dokusunun vücutta birikme şekli; elma
                    tip ve armut tip olmak üzere ikiye ayrılabilir. Elma tip
                    obezitede yağ göbek çevresinde birikmektedir. Armut tip
                    obezitede ise kalça ve basenlerde biriktiği gözlemlenir.
                    Fakat göbek çevresinde biriken yağın, kalça ve basenlere
                    göre daha tehlikeli ve kalp hastalıklarına yakalanma
                    riskinin daha yüksek olduğu kabul edilir.
                </p>
            </div>
        </div>
    </div>
</template>

<script>
import { ref, computed } from "vue";
export default {
    setup() {
        const valuex = ref(0);

        const proveActive = computed(() => {
            return valuex.value;
        });

        return {
            valuex,
            proveActive,
        };
    },
};
</script>

<style lang="scss">
.body-mass-info {
    margin: 10px auto;
    border: 1px solid rgba(116, 19, 185, 0.776);
    padding: 10px;
    border-radius: 5px;
    background-color: rgba(12, 109, 109, 0.299);

    &:hover {
        background-color: rgba(12, 109, 109, 0.5);
        cursor: pointer;
        box-shadow: 1px 1px 10px rgba(112, 13, 199, 0.5);
    }
}
.body-mass-info-red {
    background-color: rgba(255, 0, 0, 0.5);
    box-shadow: 1px 1px 10px rgba(255, 0, 0, 0.5);
}

.info-obez {
    margin: 10px auto;
    p {
        text-align: left;
    }
}
h2 {
    color: rgba(237, 162, 162, 0.789);
    text-shadow: 1px 1px 1px rgb(56, 54, 54), 0 0 25px blue,
        0 0 5px rgba(7, 7, 185, 0.781);
}
.row {
    margin: auto;
}
</style>

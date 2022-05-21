<template>
    <section class="game_phone">
        <div class="game_phone_display">
            <div class="game_phone_card">
                <div class="card_phone_top">
                    <p class="card_phone_title"></p>
                    <img class="card_phone_title_icon game_none" src="">
                </div>
                <div class="card_phone_mid">
                    <img class="card_phone_img" src="">
                </div>
                <div class="card_phone_bot">
                    <p class="card_phone_txt"></p>
                </div>
            </div>

            <div class="game_phone_input">
                <input class="game_phone_btn" type="button" value="Start" @click="game_phone">
                <div class="game_phone_info">
                    <p class="game_phone_was">Wait and see</p>
                    <p class="game_phone_was_counter">{{ card_phone_was }} / 4</p>
                    <p class="game_phone_card_rest">Carte(s)<br>restante(s)</p>
                    <p class="game_phone_card_rest_counter">{{ card_phone_number_left }} / 107</p>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    methods: {

        game_phone() {
            
            if (this.game_phone_start == 0) {
                document.querySelector(".game_phone_btn").value = "NEXT"
                this.game_phone_start = 1
                document.querySelector(".card_phone_title_icon").classList.toggle("game_none")
            }

            if (this.game_phone_start == 1) {
                if (this.card_phone_number_left != 0) {

                    this.card_phone_number = this.getRandomInt(107)

                    for(let i = 0; i < this.game_phone_list_card_used.length; i++) {
                        if (this.card_phone_number == this.game_phone_list_card_used[i]) {
                            this.card_phone_number = this.getRandomInt(107)
                            i = -1
                        }
                    }
                    this.game_phone_list_card_used.push(this.card_phone_number)
                    this.card_phone_number_left -= 1

                    this.game_phone_card_display(this.card_phone_number)
                }

                if (this.card_phone_number_left == 0) {
                    document.querySelector(".game_phone_btn").value = "FINISH"
                }
            }

        },

        game_phone_card_display (number) {
            if (number == 0 || number == 1 || number == 2) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[0]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_action.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 2 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[0]
            }
            if (number == 3 || number == 4) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[1]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 3 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[1]
            }
            if (number == 5) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[2]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 4 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[2]
            }
            if (number == 6 || number == 7) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[3]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 5 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[3]
            }
            if (number == 8 || number == 9) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[4]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 6 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[4]
            }
            if (number == 10) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[5]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 7 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[5]
            }
            if (number == 11 || number == 12 || number == 13) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[6]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 8 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[6]
            }
            if (number == 14) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[7]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 9 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[7]
            }
            if (number == 15) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[8]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 10 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[8]
            }
            if (number == 16) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[9]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 11 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[9]
            }
            if (number == 17 || number == 18) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[10]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 12 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[10]
            }
            if (number == 19 || number == 20) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[11]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 13 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[11]
            }
            if (number == 21 || number == 22) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[12]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 14 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[12]
            }
            if (number == 23) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[13]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 15 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[13]
            }
            if (number == 24 || number == 25 || number == 26) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[14]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 16 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[14]
            }
            if (number == 27 || number ==28) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[15]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 17 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[15]
            }
            if (number == 29) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[16]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 18 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[16]
            }
            if (number == 30 || number == 31) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[17]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 19 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[17]
            }
            if (number == 32) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[18]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 20 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[18]
            }
            if (number == 33) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[19]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 21 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[19]
            }
            if (number == 34 || number == 35) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[20]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 22 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[20]
            }
            if (number == 36) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[21]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 23 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[21]
            }
            if (number == 37) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[22]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 24 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[22]
            }
            if (number == 38 || number == 39) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[23]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 25 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[23]
            }
            if (number == 40 || number == 41) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[24]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 26 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[24]
            }
            if (number == 42) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[25]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 27 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[25]
            }
            if (number == 43 || number == 44 || number == 45) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[26]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 28 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[26]
            }
            if (number == 46) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[27]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 29 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[27]
            }
            if (number == 47) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[28]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 30 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[28]
            }
            if (number == 48) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[29]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 31 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[29]
            }
            if (number == 49) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[30]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 32 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[30]
            }
            if (number == 50 || number == 51) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[31]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 33 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[31]
            }
            if (number == 52 || number == 53) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[32]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 34 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[32]
            }
            if (number == 54 || number == 55) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[33]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 35 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[33]
            }
            if (number == 56 || number == 57) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[34]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 36 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[34]
            }
            if (number == 58 || number == 59 || number == 60) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[35]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 37 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[35]
            }
            if (number == 61 || number == 62 || number == 63) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[36]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 38 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[36]
            }
            if (number == 64 || number == 65 || number == 66 || number == 67) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[37]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 39 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[37]
            }
            if (number == 68 || number == 69 || number == 70 || number == 71 || number == 72) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[38]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 40 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[38]
            }
            if (number == 73) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[39]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 41 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[39]
            }
            if (number == 74) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[40]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 42 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[40]
            }
            if (number == 75) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[41]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 43 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[41]
            }
            if (number == 76 || number == 77 || number == 78 || number == 79) {
                this.card_phone_was += 1
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[42]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 44 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[42]
            }
            if (number == 80) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[43]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 45 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[43]
            }
            if (number == 81) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[44]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 46 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[44]
            }
            if (number == 82 || number == 83 || number == 84) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[45]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 47 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[45]
            }
            if (number == 85 || number == 86 || number == 87) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[46]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 48 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[46]
            }
            if (number == 88) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[47]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 49 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[47]
            }
            if (number == 89 || number == 90) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[48]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 50 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[48]
            }
            if (number == 91) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[49]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 51 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[49]
            }
            if (number == 92) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[50]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 52 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[50]
            }
            if (number == 93) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[51]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 53 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[51]
            }
            if (number == 94 || number == 95 || number == 96) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[52]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 54 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[52]
            }
            if (number == 97 || number == 98) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[53]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 55 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[53]
            }
            if (number == 99 || number == 100 || number == 101) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[54]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 56 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[54]
            }
            if (number == 102 || number == 103) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[55]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 57 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[55]
            }
            if (number == 104) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[56]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 58 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[56]
            }
            if (number == 105 || number == 106) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[57]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 59 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[57]
            }
            if (number == 107) {
                document.querySelector(".card_phone_title").innerHTML = this.titre_phone[58]
                document.querySelector(".card_phone_title_icon").src = "/logo/logo_defi.png"
                document.querySelector(".card_phone_img").src = "/rond/" + 60 + ".png"
                document.querySelector(".card_phone_txt").innerHTML = this.challenge_phone[58]
            }
        },

        getRandomInt(max) {
            return Math.floor(Math.random() * max);
        },
        
    },
    data() {
        return {

            card_phone_number : 0,
            card_phone_number_left : 107,
            card_phone_was : 0,
            game_phone_start : 0,
            game_phone_list_card_used : [],

            card_phone_title : "",
            card_phone_icon : "",
            card_phone_img : "",
            card_phone_txt : "",

            titre_phone : [
                'action/vérité',
                'alcoolique anonyme',
                'balance',
                'blague/débat',
                'step mom',
                'bryan',
                'potion magique',
                'coach',
                'dan',
                'dragibo',
                'esclave',
                'fantasme',
                'gamerz',
                'gaëtan-san',
                'glou glou I',
                'gragas',
                'groles',
                'correcteur automatique',
                'ivrogne I',
                'ivrogne II',
                'je n’ai jamais',
                'jonathan',
                'julien',
                'loi',
                'loverz',
                'minou',
                'pillier de bar',
                'pogo',
                'pour combien',
                'raph',
                'rédempteur',
                'shifumi',
                'il va faire tout noir!',
                'tir fratricide',
                'toilettes',
                'tournée générale I',
                'tournée générale II',
                'tournée générale III',
                'tournée générale IV',
                'trou I',
                'trou II',
                'trou III',
                'wait and see ?!!',
                'zephyr 21',
                'meilleurs amis!',
                'roulette russe',
                'glou glou II',
                'gros cerveau',
                'on ira le voir',
                'homme de fer',
                'homme de bronze',
                'nectar divin',
                'la fine équipe',
                'cadavres',
                'tour de table',
                'fondu de boisson',
                'samoch’',
                'bff',
                'bain de bouche',
            ],

            challenge_phone : [
                'la personne à ta gauche te demande<br>"action ou vérité?"<br><br>si tu ne veux pas dire la vérité ou<br>faire le gage, tu bois 3 gorgées',
                'tu ne bois plus pendant 3 tours<br><br>une fois le temps imparti écoulé,<br>tu bois tout ce que tu as esquivé<br>durant ces 3 derniers tours',
                'tu dois deviner le poid de la personne<br>à ta gauche<br><br>tu bois une gorgée tous les 2kg<br>de différence',
                'tu racontes une blague ou lance<br>un débat<br><br>si tu n’es pas drôle, tu bois 2 gorgées<br>ou si tu fais partis de la minorité<br>du débat, tu bois 3 gorgées',
                'entre la personne à ta droite et celle<br>à ta gauche,<br>qui préfèrais-tu avoir comme<br>beau-père / belle-mère<br><br>l’heureux élu distribue 2 gorgées',
                'tu enlèves autant de vêtements<br>que tu le veux<br><br>pour chaque vêtements enlevé tu<br>distribues 3 gorgées<br><br>(6gorgées max par personne)',
                'tous les effets néfastes sur toi se<br>dissipent<br><br>si tu n’as pas d’effet négatif,<br>tu bois 1 gorgées car tu es trop pur',
                'tu deviens le coach<br><br>si une personne ne veut pas boire,<br>tu peux lui proposer de faire des<br>exercices physique à la place',
                'tu distribues 18 gorgées<br><br>(6 max par personne)',
                'tu fais un "je te tiens tu me tiens la<br>barbichette" avec dragibo<br><br>si tu perds, tu bois 3 gorgées<br>si tu gagnes, tu distribues 2 gorgées',
                'tu désignes un esclave et boit autant de<br>gorgées qu’il y a de personnes entre<br>vous pour l’acheter<br><br>pendant 3 tours il boira à ta place',
                'tu avoues un fantasme;<br>les autres joueurs lèvent la main<br>s’ils ont le même<br><br>la minorité boit 2 gorgées',
                'entre la personne à ta droite et celle<br>à ta gauche, qui est la plus nul aux<br>jeux vidéo ?<br><br>le gros naze boit 2 gorgées',
                'tu deviens le barman<br>lorsque quelqu’un n’a plus à boire<br>tu dois le resservir<br><br>si tu oublies de servir quelqu’un,<br>tu bois 2 gorgées',
                'tout le monde boit 2 gorgées !',
                'pendant 2 tours,<br>tu bois le double de gorgées<br><br>bois en déjà 2 (seulement) dès<br>maintenant pour t’échauffer',
                'tu dois donner la pointure<br>des personnes à tes côtés<br>tu bois la différence avec<br> la vrai taille',
                'à chaque gros mot,<br>tu bois une gorgée',
                'tu dis la dernière fois que tu as bu<br>(hormis aujourd\'hui)<br>ceux qui n’ont pas bu depuis cette date<br>boivent 3 gorgées',
                'tu dis la dernière fois que tu as bu<br>(hormis aujourd\'hui)<br>ceux qui n’ont pas bu depuis cette date<br>boivent 5 gorgées',
                'tu racontes un "je n’ai jamais"<br>ceux à qui c’est arrivé boivent<br>3 gorgées',
                'tu deviens zen<br><br>tu bois 2 shots en poker face pour nous<br>montrer ta zénitude<br><br>si le peuple juge que tu n’es pas assez<br>zen, tu recommences !',
                'tu fais un bras de fer contre julien<br>si tu perds, tu bois 3 gorgées<br><br>en cas de refus, tu cul-sec',
                'vous imposez une nouvelle règle',
                'tu désignes 2 personnes<br>qui seront en couple<br><br>quand l’une bois,<br>l’autre doit aussi boire',
                'fais un cul-sec de lait (25 cl)<br>ou<br>finis un shot en léchouillant comme<br>un chat',
                'tu bois 4 gorgées<br>si cela finit ton verre,<br>tu re-pioche une carte',
                'tu dois donner la taille de ton sexe<br>au repos, si tu refuses ou que tu es<br>une femme, tu bois 4 gorgées<br><br>si tu montres ta bite ou ta foufoune,<br>tout le monde cul-sec',
                'tu désignes 1 personnes avec qui<br>tu fais un pour combien<br>ton collègue définis sur combien vous jouez et toi le nombre de<br>gorgées à boire<br><br>il n’y a pas de gagnant,<br>si vous dites le même nombre,<br><br>vous buvez tous les 2',
                'tu dois payer un fast-food à quelqu’un<br>ou<br>tu cul-sec',
                'soit tu libères une personne d’un effet<br>négatif, soit tu bois 2 gorgées<br><br>si personnes n’a d’effet négatif,<br>tu distribues 2 gorgées',
                'tu désignes une personnes pour<br>faire un "pierre-feuille-ciseaux"celui qui perd bois 3 gorgées',
                'tu ne dois pas parler pendant 2 tour<br>sinon tu bois 3 gorgées<br><br>"ta gueule!"',
                'dès que c’est ton tour,<br>les personnes à ta droite et à ta<br>gauche boivent 1 gorgées',
                'tu peux aller aux toilettes',
                'vous distribuez 2 gorgées',
                'vous distribuez 3 gorgées',
                'vous distribuez 4 gorgées',
                'vous distribuez 5 gorgées',
                'tu désignes une personne pour faire<br>un cul-sec<br>ou<br>tout le monde boit 2 gorgées',
                'tu désignes 2 personnes pour faire<br>un cul-sec avec toi<br>ou<br>tout le monde boit 3 gorgées',
                'tu désignes 1 personne qui<br>doit cul-sec<br>ou<br>tout le monde boit 4 gorgées',
                'tu bois autant de gorgées qu’il<br>y a eu de cartes<br>"wait and see ?!!" piochées<br><br>à la 4ème carte piochée,<br>tu cul-sec ton verre',
                'tout le monde boit +2 pendant 3 tours<br><br>ou<br><br>tout le monde boit +4 pendant 1 tour',
                'tu choisis ton meilleur ami<br>quand vous devez boire, vous pouvez<br>vous partager les gorgées comme bon<br>vous semble<br>pour fêter votre amitié,<br>buvez-en 2 dès maintenant',
                'tu désignes 3 personnes<br>servez 4 shots<br>(3 avec de l’eau, 1 avec de l’alcool)<br>mélangez les verres<br>servez vous!',
                'tout le monde boit 3 gorgées !',
                'tout le monde s’appelle par son<br>nom complet<br>si quelqu’un oublie de le faire<br>il boit 2 gorgées',
                'regarde les 3 prochaines cartes du<br>paquet<br><br>mets les dans l’ordre que tu veux',
                'tu fais un tourbillon avec une bière si c’est un succès, tous les autres<br>joueurs boivent 2 gorgées si c’est un échec, tu fais un shot',
                'cul-sec ton verre<br><br>si c’est une réussite, tous les autres<br>joueurs boivent +2 pendant 2 tours<br><br>si c’est un échec, tu bois +3 pendant<br>1 tour',
                'tu peux boire 1 verre d’eau<br><br>si tu as un meilleure ami il peut boire<br>1 verre d’eau avec toi',
                'tu bois 1 gorgée, la personne à ta<br>gauche 2, et ainsi de suite jusqu’à<br>finir la boucle',
                'tu finis les 2 verres les moins<br>remplis',
                'tu bois 1 gorgée par personne qui<br>joue au jeu en ce moment',
                'sers toi un 2ème verre, tu dois l’avoir<br>finis avant ton prochain tour<br><br>si tu n’as pas réussi dans le temps<br>impartis, tu le cul-sec',
                'si tu aimes le ricard,<br>tu bois 3 gorgées<br><br>si tu n’aimes pas le ricard,<br>tu bois 6 gorgées',
                'tu dois donner la date de naissance<br>de la personne à ta droite<br><br>si tu ne la connais pas,<br>tu bois 3 gorgées',
                'tu gargarises 1 shot d’alcool<br><br>après 3 secondes, tu l’avales',
            ]
        }
    },
}

</script>

<style>
    .game_phone {
        width: 100%;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .game_phone_display {
        height: 90vh;
        width: 90%;
        max-width: 400px;
    }

    .game_phone_card {
        height: 70vh;
        width: 100%;
        background-image: url('../assets/img/background/fond_2.png');
        background-size: cover;
        background-repeat: no-repeat;
        border: solid 10px black;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        border-radius: 1rem;
    }

    .card_phone_top {
        display: flex;
        align-items: center;
        min-height: 3.5rem;
        margin: 0.5rem 0.5rem -0.75rem 0.5rem;
        padding: 0.25rem;
        background-color: rgb(255, 255, 255, 0.5);
        border: solid 4px black;
        border-radius: 0.4rem;
    }

    .card_phone_title {
        width: 100%;
        font-size: 1.25rem;
        text-align: center;
    }

    .card_phone_title_icon {
        height: 2.5rem;
        width: 2.5rem;
    }

    .card_phone_mid {
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .card_phone_img {
        width: 85%;
    }

    .card_phone_bot {
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
        font-size: 0.75rem;
        margin: 0rem 0.5rem 0.5rem 0.5rem;
        padding: 1rem 0rem;
        min-height: 10rem;
        background-color: rgb(255, 255, 255, 0.5);
        border: solid 4px black;
        border-radius: 0.4rem;
    }

    .game_phone_input {
        height: 15vh;
        margin-top: 5vh;
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .game_phone_btn {
        width: 40%;
        height: 80%;
        border: 0;
        border-radius: 1.5rem;
        font-size: 1.5rem;
    }

    .game_phone_info {
        text-align: center;
        width: 50%;
    }

    .game_phone_was {
        font-size: 0.75rem;
    }

    .game_phone_was_counter {
        font-size: 1.25rem;
    }

    .game_phone_card_rest {
        font-size: 0.75rem;
        margin-top: 0.5rem;
    }

    .game_phone_card_rest_counter {
        font-size: 1.25rem;
    }

    .game_none {
        display: none;
    }

    @media screen and (max-height: 720px) {
        .card_phone_img {
            width: 75%;
        }
    }

    @media screen and (max-height: 670px) {
        .card_phone_img {
            width: 65%;
        }
    }

    @media screen and (max-height: 630px) {
        .card_phone_img {
            width: 55%;
        }
    }

</style>
<template>
  <div class="hello">
    
    <h2>{{title}}</h2>

    <h2>Skor : {{skor}} </h2>

    <h2 v-if="skor > 60">Wow LULUS, Anda keren</h2>
    <h2 v-else>Anda GAGAL, Ayo semangat</h2>

    <div v-for="(quiz, indexquiz) in questions">

        <b><p>{{indexquiz+1}}. {{quiz.text}}</p></b>

            <div v-for="(choosed) in quiz.responses">

                <input type="radio" @click="checkAnswer(indexquiz,choosed)" :name="indexquiz" :value="choosed">

                <span v-text="choosed"></span>

            </div>
    </div>

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      title: 'QUIZ APP',
      skor: 0,
      right_answer : [],
      questions: [
          {
            text: "Matematika: 1 + 1 =",
            responses: [
              "1","2","3","4"
            ],
            correct: "2"
          }, 
          {
            text: "Bahasa Indonesia: Majas yang mengungkapkan benda mati seolah benda hidup adalah",
            responses: [
              "Simbolik","Hiperbola","Litotes","Personifikasi",
            ],
            correct: "Personifikasi"
          },
          {
            text: "Bahasa Inggris: Synonym of good",
            responses: [
              "Bad","Low","Excellent","Wicked",
            ],
            correct: "Excellent"
          },
          {
            text: "Agama islam: Tanggal lahirnya nabi Muhammad SAW ... Rabbiulawal",
            responses: [
              "11","12","18","15",
            ],
            correct: "12"
          },
          {
            text: "Musik: Vokalis dari band Queen ialah ?",
            responses: [
              "Matt Shadows","Freddie Mercury","Nial Callagar","D Axel",
            ],
            correct: "Freddie Mercury"
          },
          {
            text: "Teknologi: Apa nama android versi 8.0",
            responses: [
              "Oreo","Marshmello","Jellybean","Lollipop",
            ],
            correct: "Oreo"
          },
          {
            text: "Kartun: Siapakah teman Spongebob yang bekerja sebaga kasir Krusty Crab ?",
            responses: [
              "Pattrick","Sandy","Plankton","Sqwirdward",
            ],
            correct: "Sqwirdward"
          },
          {
            text: "Game: Tim manakah yang menjuarai TI 8 DOTA 2",
            responses: [
              "Evil Genniuses","Liquid","OG","Fnatic",
            ],
            correct: "OG"
          },
          {
            text: "Olahraga: Permainan sepak bola dimainkan berapa orang ?",
            responses: [
              "15","11","10","13",
            ],
            correct: "11"
          },
          {
            text: "Film: Ada berapa series film dari Maze Runner ?",
            responses: [
              "1","2","3","4",
            ],
            correct: "3"
          },
        ]
    }
  },
  methods : {
        checkAnswer(indexquiz,choosed){
            if(this.questions[indexquiz].correct == choosed){
                if(!this.right_answer.includes(indexquiz+1)){
                    this.right_answer.push(indexquiz+1);
                    this.skor +=10;
                }
            }
            else{
                if(this.right_answer.includes(indexquiz+1)){
                    this.right_answer.splice(indexquiz,1);
                    this.skor -=10;
                }
            }
            console.log(this.right_answer);
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>

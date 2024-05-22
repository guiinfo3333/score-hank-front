<script lang="ts">
import Card from "@/components/card/Card.vue";
import Title from "@/components/titile/Title.vue";
import TitleRight from "@/components/titile/TitleRight.vue";
import Team from "@/components/teams/Team.vue";
import Flex from "@/components/contents/Flex.vue"

export default {
  name: 'HomeView',
  components: {
    Title,
    TitleRight,
    Team,
    Flex,
    Card,
  },
  data() {
    return {
      teams: [
        {
          name: 'Palmeiras',
          imgSrc: '/src/assets/escudos-time/palmeiras.png',
        },
        {
          name: 'Flamengo',
          imgSrc: '/src/assets/escudos-time/flamengo.png',
        },
        {
          name: 'Vitória',
          imgSrc: '/src/assets/escudos-time/vitoria.png',
        },
        {
          name: 'Grêmio',
          imgSrc: '/src/assets/escudos-time/gremio.png',
        },
      ],
      matches: [
        {
          homeTeam: 'atletico-goianiense',
          awayTeam: 'palmeiras',
          message: 'Probabilidade maior de vitória do time da casa',
        },
        {
          homeTeam: 'flamengo',
          awayTeam: 'fluminense',
          message: "Probabilidade maior de vitória do time visitante",
        },
        {
          homeTeam: 'bragantino',
          awayTeam: 'corinthians',
          message: 'Probabilidade maior de vitória do time da casa',
        },
        {
          homeTeam: 'gremio',
          awayTeam: 'internacional',
          message: "Probabilidade maior de vitória do time visitante",
        },
        {
          homeTeam: 'juventude',
          awayTeam: 'vasco',
          message: "Probabilidade maior de vitória do time visitante",
        },
        {
          homeTeam: 'sao_paulo',
          awayTeam: 'vitoria',
          message: "Probabilidade maior de vitória do time visitante",
        },
        {
          homeTeam: 'fortaleza',
          awayTeam: 'fluminense',
          message: "Probabilidade maior de vitória do time visitante",
        },
      ],
    };
  },
};

</script>

<template>
  <div class="container-hank">
    <div class="menu1"></div>
    <div class="body1">
      <Title message="Previsões da próxima rodada"></Title>
      <div class="container-results">
        <Card v-for="(match, index) in matches">
          <template #content>
            <Flex>
              <template #content>
                <Team :name="match.awayTeam"></Team>
                <span>vs</span>
                <Team :name="match.homeTeam"></Team>
              </template>
            </Flex>
            <Flex>
              <template #content>
                <h1>{{match.message}}</h1>
              </template>
            </Flex>
          </template>
        </Card>
      </div>
    </div>
    <div class="menu2">
      <TitleRight message="Times"></TitleRight>
      <div class="times" v-for="(team, index) in teams">
        <img :src=team.imgSrc class="img-times"/>
        <div>
           <span>{{ team.name }}</span>
           <span>Estatísticas</span>
        </div>
        <span>Ver</span>
      </div>
    </div>
  </div>
</template>


<style scoped>
h1 {
  padding-top: 20px;
  font-family: 'Roboto', sans-serif;
  font-size: 1.2rem;
  font-weight: 400;
}
.container-hank{
  display: grid;
  width: 100vw;
  height: 100vh;
  position: relative;
  grid-template-columns: 250px 1fr 256px;
}

.menu1 {
  background: white;
  border-right: 1px solid var(--border-right);
}

.menu2 {
  background: white;
  border-left: 1px solid var(--border-right);
}
.container-results{
  align-items: center;
  display: flex;
  flex-direction: column;
  gap:34px;
}

.times {
  margin-top: 33px;
  padding-left: 18px;
  display: flex;
  gap: 14px;
}

.times div {
  padding-top: 5px;
  display: flex;
  flex-direction: column;
}

.times div span:nth-child(1) {
  font-family: 'Roboto', sans-serif;
  font-size: 1.1rem;
  color: black;
}

.times div span:nth-child(2) {
  font-family: 'Roboto', sans-serif;
  font-size: 0.8rem;
  color: #7D7D7D;
}

.times span:nth-child(3) {
  padding-top: 17px;
  font-family: 'Roboto', sans-serif;
  font-size: 0.9rem;
  color: #0095F6;
}

.times span:nth-child(3):hover {
  cursor: pointer;
}

.img-times{
  width: 51px;
  height: 51px;
}
</style>

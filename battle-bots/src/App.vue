 <template>
  <div id='app'>
        <section v-if='!showBots' class='create-section'>
          <button @click='switchScreen'>Bot List</button>
      <h1>Create Bot</h1>
              Bot Name: <input v-model='botName' type="text" name="name" id=""> 
              <br>  
             Bot Health: <input v-model="botHealth" type="text" name="health" id="">
              <br>
             Bot Attack: <input v-model="botAttack" type="text" name="attack" id=""> 
             <br>
             <button @click='newBot'>Create</button>


        </section>
        <section v-else>
            <button @click='switchScreen'>Create Bot</button>
          <h1>Bot List</h1>
          <bot-list :bots ='bots' ></bot-list>
        </section>
  </div>
</template>

<script>
import BotList from "./components/Bots/BotList";
export default {
  components: {
    botList: BotList
  },

  data() {
    return {
      botName: "",
      botHealth: "",
      botAttack: "",
      id: 0,
      bots: [],
      showBots: false
    };
  },

  methods: {
    newBot() {
      this.id++;
      let newBot = {
        name: this.botName,
        health: this.botHealth,
        attack: this.botAttack,
        id: this.id
      };
      this.bots.push(newBot);
      this.botName = "";
      this.botHealth = "";
      this.botAttack = "";
    },
    switchScreen() {
      this.showBots = !this.showBots;
    }
  }
};
</script>
<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1,
h2 {
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
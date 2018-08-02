 <template>
  <div>
      <bot :battleBots = 'battleBots'></bot>
      <div v-for='(bot) in bots' :key='bot.id' >
         <p>Bot Name: {{bot.name}}</p>
         <p>Health: {{bot.health}}</p>
          <p>Attack: {{bot.attack}}</p>
          <button @click='addToBattle(bot.id)'>Select</button>
         <hr>
      </div>
  </div>
</template>

<script>
import Bot from './Bot'
export default {
  props: ["bots"],

  components: {
      bot: Bot
  },

  data() {
    return {
      battleBots: []
    };
  },

  methods: {
   addToBattle(id) {
     for (let i = 0; i < this.bots.length; i++) {
       if (id === this.bots[i].id) {
         this.battleBots.push(this.bots[i]);
         console.log('added', this.battleBots)
       }
     }
   }
  }
};
</script>

<style>

</style>
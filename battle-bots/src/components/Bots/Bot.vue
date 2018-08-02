 <template>
  <div>
      <div v-for='bot in battleBots' :key='bot.id'>
        <p>Selected: {{bot.name}}</p>
      </div>
  </div>
</template>

<script>
export default {
props: ['battleBots']
}
</script>

<style>

</style>
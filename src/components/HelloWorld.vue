<template>
  <div class="hello">
    <div v-for="(item, index) in items" :key="index">
      <ul>
        <div v-if="item.datumRodjenja !== ''">
          <li>{{ item.vrsta }} {{ item.ime }} {{ item.datumRodjenja }}</li>
        </div>
        <div v-else-if="item.datumRodjenja === null">
          <li>{{ item.vrsta }} {{ item.ime }} Nepoznat</li>
        </div>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      headers: ["Nº", "Name", "Gender"],
      items: [
        {
          vrsta: "lav",
          ime: "lazar",
          datumRodjenja: Date.now(),
        },
        {
          vrsta: "macka",
          ime: "milos",
          datumRodjenja: Date.now(),
        },
        {
          vrsta: "pas",
          ime: "bane",
          // datumRodjenja: Date.now(),
        },
        {
          vrsta: "krokodil",
          ime: "nemanja",
          datumRodjenja: Date.now(),
        },
        {
          vrsta: "zec",
          ime: "dragan",
          datumRodjenja: Date.now(),
        },
      ],
    };
  },
  methods: {},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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

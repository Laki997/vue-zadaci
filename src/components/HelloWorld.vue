<template>
  <div class="hello">
    <div v-for="(item, index) in items" :key="index">
      <ul>
        <div v-if="item.datumRodjenja !== null">
          <div>
            <button @click="removeElement(item)">Remove</button>
            <button type="submit">Move to top</button>
            <li>{{ item.vrsta }} {{ item.ime }} {{ item.datumRodjenja }}</li>
          </div>
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
          datumRodjenja: new Date("2012-02-03"),
        },
        {
          vrsta: "macka",
          ime: "milos",
          datumRodjenja: new Date("2012-02-03"),
        },
        {
          vrsta: "pas",
          ime: "bane",
          // datumRodjenja: Date.now(),
        },
        {
          vrsta: "krokodil",
          ime: "nemanja",
          datumRodjenja: new Date("2012-02-03"),
        },
        {
          vrsta: "zec",
          ime: "dragan",
          datumRodjenja: new Date("2012-02-03"),
        },
      ],
    };
  },
  methods: {
    removeElement: function(index) {
      this.items.splice(index, 1);
    },
  },
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

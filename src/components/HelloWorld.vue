<template>
  <div class="hello">
    <div>
      <form id="app" v-on:submit.prevent="onSubmit">
        Vrsta<input
          type="text"
          id="vrsta"
          v-model="items.vrsta"
          name="items.vrsta"
        />
        Ime<input type="text" id="ime" v-model="items.ime" name="items.ime" />
        Datum rodjenja<input
          type="text"
          id="datumRodjenja"
          v-model="items.datumRodjenja"
          name="items.datumRodjenja"
        />
        <button type="submit">Add Animal</button>
      </form>
    </div>
    <div v-for="(item, index) in items" :key="index">
      <ul>
        <div>
          <div>
            <button @click="moveElement(index)">Move to top</button>
            <button @click="removeElement(index)">Remove</button>
            <li v-if="item.datumRodjenja !== undefined">
              {{ item.vrsta }} {{ item.ime }} {{ item.datumRodjenja }}
            </li>

            <li v-if="item.datumRodjenja === undefined">
              {{ item.vrsta }} {{ item.ime }} Nepoznat
            </li>
          </div>
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
    moveElement: function(index) {
      let prvi = this.items[0];
      console.log(prvi);
      let element = this.items[index];
      console.log(element);
      let bubble;
      bubble === element;
      element === prvi;
      prvi === bubble;
    },
    onSubmit() {
      let item = {
        vrsta: this.items.vrsta,
        ime: this.items.ime,
        datumRodjenja: this.items.datumRodjenja,
      };

      this.items.push(item);
    },
    nullItems: function() {
      return this.items.filter(function(item) {
        return item[2] === null;
      });
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

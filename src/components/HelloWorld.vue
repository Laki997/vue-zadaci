<template>
  <div class="hello">
    <div>
      <form @submit="onSubmit()">
        Vrsta <input type="text" name="" id="vrsta" /> Ime<input
          type="text"
          id="ime"
        />
        Datum rodjenja<input
          type="text"
          id="datumRodjenja"
          name="datumRodjenja"
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
      let vrsta = document.getElementById("#vrsta");
      let ime = document.getElementById("#ime");
      let godine = document.getElementById("#godine");
      console.log(vrsta, ime, godine);
      this.items.push(vrsta, ime, godine);
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

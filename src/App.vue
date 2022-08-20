<template>
  <div id="app">
    <p class="title">GAMES SEARCH</p>
    <div class="input_contain">
      <input v-model="search" type="text" placeholder="Filter Games" />
    </div>
    <div class="grid">
      <div v-for="game in filteredGames" class="grid_item">
        <div class="image_contain">
          <img :src="game.image" alt="" />
        </div>
        <p class="games_name">{{ game.name }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import { computed } from "vue";

export default {
  name: "app",
  data() {
    return {
      games: [
        {
          id: 1,
          name: "god of war",
          image:
            "https://www.gamespew.com/wp-content/uploads/2017/12/God-of-War-min.jpg"
        },
        {
          id: 2,
          name: "Tom Raider",
          image:
            "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSymqVtN9YADem838_GMc5PPJmMdEH7Fh-YKg&usqp=CAU"
        },
        {
          id: 3,
          name: "The Last of Us",
          image:
            "https://imageio.forbes.com/specials-images/imageserve/613a1fa90a58b992ccce0204/The-Last-Of-Us-Movie-Behind-The-Scenes/960x0.jpg?format=jpg&width=960"
        },
        {
          id: 4,
          name: "Call of Duty",
          image:
            "https://www.imagediamond.com/blog/wp-content/uploads/2019/11/Call-of-duty-images-20208.jpg"
        },
        {
          id: 5,
          name: "Mordern Combat",
          image:
            "https://m.media-amazon.com/images/M/MV5BMWI3MTg0ODctZGZmYy00ZGI4LTk3NmItZjhkZTgzMWE5NDczXkEyXkFqcGdeQXVyNTgyNTA4MjM@._V1_FMjpg_UX1000_.jpg"
        },
        {
          id: 6,
          name: "Witcher",
          image:
            "https://images2.minutemediacdn.com/image/fetch/w_2000,h_2000,c_fit/https%3A%2F%2Fwinteriscoming.net%2Ffiles%2F2018%2F08%2FGeralt-Witcher.jpg"
        },
        {
          id: 7,
          name: "Watch Dogs",
          image:
            "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQYX1hOO1OtF4ZCg1FAC8Jgb7qgzH3QM6FZIiI27LLb4VWm3wrm2RXh2_ZrtW6GxMSBX7o&usqp=CAU"
        },
        {
          id: 8,
          name: "Infamous",
          image:
            "https://www.giantbomb.com/a/uploads/scale_small/45/459166/3216007-infamous.jpg"
        },
        {
          id: 9,
          name: "Mortal Kombat",
          image:
            "https://play-lh.googleusercontent.com/FHyo-8OuAN3P6_wJi21bayf8KltZ_ZWpE7n6M5lROrl-U3QeSjvbgi8clOhdaY_M5jY"
        },
        {
          id: 10,
          name: "Need for Speed",
          image: "https://i.ytimg.com/vi/K-5EdHZ0hBs/maxresdefault.jpg"
        },
        {
          id: 11,
          name: "Gran Turismo",
          image:
            "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRMW5rMJDYc_2j82dtTmdKwRn0G3oAGCzLbCHcQQclT&s"
        },
        {
          id: 12,
          name: "Uncharted",
          image:
            "https://m.media-amazon.com/images/M/MV5BMTYzYzIxMjktMDM4NS00MTM5LWJlMDgtNDRhMDNhOGRmY2EwXkEyXkFqcGdeQXVyMTk2OTAzNTI@._V1_.jpg"
        }
      ],
      search: ""
    };
  },

  computed: {
    filteredGames() {
      return this.games.filter(game => {
        return game.name.match(this.search);
      });
    }
  }
};
</script>

<style>
#app {
  font-family: "Bigelow Rules";
  background: linear-gradient(
    to left,
    rgba(7, 27, 82, 1) 0%,
    rgba(0, 128, 128, 1) 100%
  );
  padding: 20px;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
}
img {
  width: 100%;
  height: 100%;
}
.title {
  color: #0ccac4;
  font-size: 3rem;
  font-weight: 600;
}
.grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  gap: 20px;
}

.grid_item {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: #95dada;
  border: 1px solid grey;
  border-radius: 5px;
  padding: 10px;
  cursor: pointer;
  -moz-osx-font-smoothing: grayscale;
  backface-visibility: hidden;
  transform: translateZ(0);
  transition: transform 0.25s ease-out;
}

.grid_item:hover {
  transform: scale(1.05);
}

.image_contain {
  width: 90%;
  height: 80%;
}

.input_contain {
  width: 100%;
  padding: 20px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 5px;
}

input {
  width: 200px;
  height: 40px;
  padding: 10px;
}

.games_name {
  font-size: 1.2rem;
  font-weight: 600;
}
@media (max-width: 1024px) {
  .grid {
    grid-template-columns: 1fr;
  }
}
</style>

<template>
  <div class="child">
    <form @submit.prevent>
      <input
        type="text"
        name=""
        id="search-input"
        placeholder="type in your search-keyword"
        class="search-bar"
        @input="searchWord"
      />
      <button class="backg" @click="searchEntries">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="16"
          height="16"
          fill="currentColor"
          class="search-icon"
          viewBox="0 0 16 16"
        >
          <path
            d="M11.742 10.344a6.5 6.5 0 1 0-1.397 1.398h-.001c.03.04.062.078.098.115l3.85 3.85a1 1 0 0 0 1.415-1.414l-3.85-3.85a1.007 1.007 0 0 0-.115-.1zM12 6.5a5.5 5.5 0 1 1-11 0 5.5 5.5 0 0 1 11 0z"
          />
        </svg>
      </button>
    </form>
  </div>
</template>

<script>
export default {
  name: "SearchInput",

  methods: {
    searchEntries() {
      this.$emit("searchEntries");
    },
    searchWord(event) {
      this.$emit("searchWord", event);
    },
  },
};
</script>

<style scoped>
.child {
  display: flex;
  justify-content: center;
  align-items: center;
}
.search-bar {
  font-size: 1rem;
  width: 120%;
  border-radius: 2rem;
  border: 2px solid var(--clr-purple-02);
  padding: 0.5rem 0.75rem;
  position: relative;
  left: -23px;
}
.search-bar:active {
  border-color: 2px solid var(--clr-purple-02);
}

.backg {
  background-color: var(--clr-purple-01);
  position: relative;
  border-radius: 2rem;
  left: 219px;
  width: 47px;
  height: 37px;
  top: -37px;
  border: none;
  cursor: pointer;
}
.backg:hover {
  color: var(--clr-black-01);
}
.search-icon {
  position: absolute;
  right: 15px;
  top: 10px;
  color: var(--clr-white-02);
}
.search-icon:hover {
  box-shadow: 2px 2px 2px 2px var(--clr-purple-1);
  opacity: 0.7;
}
</style>

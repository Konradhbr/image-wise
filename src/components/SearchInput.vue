<template>
  <div class="searchWrapper">
      <input
       id="search"
       name="search"
       :class="{dark}"
       :value="value"
       @input="handleChange"
      />
    </div>
</template>

<script>
export default {
  name: 'SearchInput',
  props: {
    value: {
      type: String,
      required: true,
    },
    dark: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    handleChange(e) {
      this.$emit('input', e.target.value);
    },
  },
};
</script>

<style lang="scss" scoped>

 .searchWrapper {
   width: 250;
   display: flex;
   flex-direction: column;
   margin-top: 50px;
   margin-bottom: 20px;
 }


  input {
    color: white;
    text-align: center;
    font-size: 18px;
    font-weight: 300;
    height: 30px;
    border: 0;
    background: none;
    border-bottom: 1px solid white;
    transition: box-shadow .3s ease-out;

    @media (min-width: 1024px) {
      font-weight: 400;
    }

  }

    input:focus {
      outline: none;
      box-shadow: 0 5px 10px -8px  white;
    }

    .dark {
      color: #1e3d4a;
      border-bottom-color: #1e3d4a;
    }
    .dark:focus {
      box-shadow: 0 10px 20px -8px rgba(#1e3d4a, .2);
    }


</style>

<template>
  <header>
        <img src="../assets/img/notflix-logo.png" alt="Not!flix Logo">
        <nav>
            <input               
                type="text" 
                placeholder="Movies, series, titles..."
                v-model="searchInput"
                @keydown.enter="$emit('search', searchInput)">
                <!-- real-time search -->
                <!-- @keyup="sendSearch()" -->
            <button @click="$emit('search', searchInput)">Search</button>
      </nav>
  </header>
</template>

<script>
export default {
    name: 'Header',
    data() {
        return {
            searchInput: ''
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/style/variables.scss';
    @import '../assets/style/mixins.scss';

    header {
        @include flex-center ('cross');        
        height: $header-height;
        padding: 0 60px; 
        background-image: linear-gradient($bg-color, (rgba($bg-color, 0.7)));

        img {
            height: 50%;
            filter: drop-shadow(0 0 10px $bg-color);
        }

        nav {
            width: 100%;
            display: flex;
            justify-content: flex-end;  
            
            input,
            button {
                padding: 10px;
                margin-left: 10px;
                font-size: 18px;
                border-radius: 10px;
                color: $text-color;
                background-color: transparent;
                border: 2px solid $brand-color;
                box-shadow: (0 0 10px $bg-color);
                outline: none;
                transition: .3s;
            }

            input:focus {
                background-color: rgba($brand-color, 0.2);              
            }

            button:hover {
                cursor: pointer;
                background-color: $brand-color;
            }
        }
    }
</style>
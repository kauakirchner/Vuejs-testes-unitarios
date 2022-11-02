<template>
  <div class="container" @click="onclickEmit">
    <span>{{ index }}</span>
    <img :src="imgUrl" alt="" class="image">
    <div>
        <div :class="{ 'current': isActiveMusic }">{{ title }}</div>
        <div class="subtitle">{{ subtitle }}</div>
    </div>
  </div>
</template>

<script>
    export default {
        name: 'SongCard',
        props: {
            index: Number,
            title: String,
            subtitle: String,
            imgUrl: String,
            isActiveMusic: Boolean
        },
        methods: {
            onclickEmit() {
                this.$emit("click-music-card", this.index);
            }
        }
    }
</script>

<style>
.container {
    display: flex;
    width: 220px;
    background-color: #333;
    padding: 8px 16px;
    gap: 16px;
    align-items: center;
    color: #fff;
    margin-top: 12px;
}
.image {
    height: 40px;
    width: 40px;
}
.subtitle {
    color: #777;
    margin-top: 12px;
    opacity: .90;
}

.current {
    color: green;
}
</style>
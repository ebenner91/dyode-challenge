<template>
    <div class="link-cards">
        <slot></slot>
    </div>
</template>

<style scoped>
    .link-cards {
        display: flex;
        align-items: center;
        justify-content: space-between;
        flex-wrap: wrap;
        padding: 20px;
    }
</style>

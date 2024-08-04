<template>
    <div class="gift">
        <div class="gift-tie-1"></div>
        <div class="gift-tie-2"></div>
        <div class="gift-top"></div>
        <div class="gift-body"></div>
    </div>
</template>
<script>
export default {
    name: 'GiftComponent',
}
</script>

<style>
.gift {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    z-index: 10;
}

.gift-top {
    width: 100px;
    height: 25px;
    background-color: #7aa944;
}

.gift-body {
    width: 90px;
    height: 60px;
    background-color: #517c20;    
}

.gift-tie-1 {
    background-color: #a52929a6;
    position: absolute;
    width: 15px;
    height: 85px;
}

.gift-tie-2 {
    background-color: #a529298e;
    top: 45px;
    position: absolute;
    width: 90px;
    height: 15px;
}
</style>
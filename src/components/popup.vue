<template>
    <div class="popup">
        <h1 class="title">Новый клиент создан</h1>
    </div>
</template>
<script>
export default {
    name: 'Popup',
}
</script>
<style>
    .popup{
        visibility: hidden;
        opacity: 0;
        transition: opacity .3s ease-in-out,visibility .3s ease-in-out;
        text-align: center;
        background:#a1dee0;
        border-radius: 2rem;
        max-width: 720px;
        margin: 10px auto;
        position: fixed;
        right: 0;
        left: 0;
        top:98px;
        height: 731px;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .popup__open{
        visibility: visible;
        opacity: 1;
        transition: opacity .3s ease-in-out,visibility .3s ease-in-out;
    }
    .title{
        margin: 0;
        color: rgb(11, 93, 139);
        font-weight: bolder;
        font-family: 'Open Sans', sans-serif;
    }

</style>
<script>
</script>
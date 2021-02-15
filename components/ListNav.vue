<template>
    <div>
        <label class="text-show">
            {{textList}}
        </label>
        <select class="list-nav">
            <option v-for="(op, index) in valueOption" 
                :key="index" 
                :value="op">
                {{op}}
            </option>
        </select>
    </div>
</template>
<script>

export default {
    props:['textList','valueOption'],
}
</script>
<style scoped>
.text-show{
    margin-left: 10px;
}
.list-nav{
    background-color: #e0e0e0;
    border: none;
    padding: 8px;
    border-radius: 5px;
    min-width: 180px;
    margin-left: 5px;
}
.list-nav:focus{
    outline-width: 0;
}
</style>
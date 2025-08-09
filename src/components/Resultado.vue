<script setup>
    const props = defineProps(['resultado'])
</script>
<template>
    <div class="row">
        <div class="col mt-5">
            <span v-show="props.resultado" class=" btn btn-success">{{props.resultado}}</span>
        </div>
    </div>
</template>
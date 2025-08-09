<script setup>
    const props = defineProps(['functionGetNumA', 'functionGetNumB', 'switch'])
</script>

<template>
    <form @submit.prevent="" >
                <div class="row mb-5 mt-5">
                    <div class="col-6 offset-3">
                        <input @keyup="props.functionGetNumA" type="number" class="form-control text-center" placeholder="Digite um numero">
                    </div>
                </div>
                <div class="row mb-5 mt-5">
                    <div class="col-6 offset-3">
                        <select @change="props.switch" class="p-2 form-control text-center">
                            <option value="soma">+</option>
                            <option value="sub">-</option>
                            <option value="mult">*</option>
                            <option value="div">/</option>
                        </select>
                    </div>
                </div>
                <div class="row">
                    <div class="col-6 offset-3">
                        <input type="number" @keyup="props.functionGetNumB" class="form-control text-center" placeholder="Digite um numero">
                    </div>
                </div>
            </form>
</template>
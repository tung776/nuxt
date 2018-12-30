<template>
    <div>
        <h2>user's id {{$route.params.id}}</h2>
    </div>
</template>
<script>
export default {
    validate (context) {
        return /^\d+/.test(context.params.id)//Chỉ chấp nhận biến id là kiểu số
    }
}
</script>

<script setup>
// 教材では↓だがinertiaが無いので、routerに変更
// import { Inertia } from '@inertiajs/inertia'
import { router } from '@inertiajs/vue3'

defineProps({
    id : String,
    blog : Object
})

const deleteConfirm = id => {
    // console.log(id)
    router.delete(`/inertia/${id}`, {
        onBefore: () => confirm('本当に削除しますか？')
    })
}

</script>
<template>
    {{ id }}です。<br>
    {{ blog.title }}<br>
    <button @click="deleteConfirm(blog.id)">削除</button>
</template>
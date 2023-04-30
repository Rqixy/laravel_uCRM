<script setup>
import { Inertia } from '@inertiajs/inertia';
import InertiaTest from '../InertiaTest.vue';

defineProps({
    id : String,
    blog: Object
})

const deleteConfirm = id => {
    // console.log(id);
    Inertia.delete(`/inertia/${id})`, {
        onBefore: () => confirm('本当に削除しますか？')
    });
}
</script>

<template>
    {{ id }}<br>
    {{ blog.title }}<br>
    <button @click="deleteConfirm(blog.id)">削除</button><br>
</template>

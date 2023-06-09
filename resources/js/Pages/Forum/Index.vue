<script setup>
import ForumLayout from '@/Layouts/ForumLayout.vue';
import Select from '@/Components/Select.vue'
import InputLabel from '@/Components/InputLabel.vue'
import { Head } from '@inertiajs/vue3';
</script>

<template>
    <Head title="Forum" />

    <ForumLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">Dashboard</h2>
        </template>

        <div class="sm:px-6 lg:px-8">
            <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                <div class="p-6 text-gray-900">
                    <div>
                        <InputLabel for="topic" value="Topic" />
                        <Select id="topic">
                            <option value="">All topics</option>
                            <option v-for="(topic, index) in $page.props.topics" :key="index" :aria-valuemax="topic.slug">
                                {{ topic.name }}
                            </option>
                        </Select>
                    </div>
                </div>
            </div>
        </div>

        <template #side>
            <div class="bg-white overflow-hidden shadow-sm sm:rounded-lg">
                <div class="p-6 text-gray-900">Side</div>
            </div>
        </template>
    </ForumLayout>
</template>

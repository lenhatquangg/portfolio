<template>
    <div class="timeline space-y-6 relative">
        <div class="absolute left-[28%] sm:left-1/4 transform -translate-x-1/2 top-0 h-full w-[2px] bg-primary"></div>

        <div v-for="(project, index) in projects" :key="index" class="event flex items-start gap-6 relative">
            <div class="timestamp text-right font-bold text-primary break-words">
                <span v-if="project.date.includes('to')">
                    <span>{{ project.date.split(' to ')[0] }}</span><br />
                    <span >---------</span><br />
                    <span>{{ project.date.split(' to ')[1] }}</span>
                </span>
                <span v-else>
                    {{ project.date }}
                </span>
            </div>
            <div class="w-4 h-4 bg-secondary rounded-full absolute left-[28%] sm:left-1/4  transform -translate-x-1/2">
            </div>

            <div
                class="ml-2 sm:ml-[14%] project flex-1 p-6 pt-0 rounded-lg shadow-md hover:shadow-xl transition-shadow duration-300">
                <h3 class="text-xl text-primary mb-4 font-bold">{{ project.name }}</h3>
                <p class="text-sm text-secondary">{{ project.description }}</p>
            </div>
        </div>
    </div>

</template>

<script setup>
defineProps({
    projects: {
        type: Array,
        required: true
    }
})
</script>
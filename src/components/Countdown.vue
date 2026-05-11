<template>
	<div class="countdown">
		<div class="counter" aria-live="polite">
			<span class="time">{{ days }}d</span>
			<span class="sep">:</span>
			<span class="time">{{ hours }}h</span>
			<span class="sep">:</span>
			<span class="time">{{ minutes }}m</span>
			<span class="sep">:</span>
			<span class="time">{{ seconds }}s</span>
		</div>
	</div>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

// target date — default to 3 days from now for demo purposes
const now = new Date()
const defaultTarget = new Date(now.getTime() + 3 * 24 * 60 * 60 * 1000)

const props = defineProps<{ target?: string | number | Date }>()
const targetDate = ref<Date>(props.target ? new Date(props.target as any) : defaultTarget)

const days = ref('0')
const hours = ref('0')
const minutes = ref('0')
const seconds = ref('0')

let timer: number | undefined

function update() {
	const diff = Math.max(0, targetDate.value.getTime() - Date.now())
	const s = Math.floor(diff / 1000)
	const d = Math.floor(s / 86400)
	const h = Math.floor((s % 86400) / 3600)
	const m = Math.floor((s % 3600) / 60)
	const sec = s % 60

	days.value = String(d)
	hours.value = String(h).padStart(2, '0')
	minutes.value = String(m).padStart(2, '0')
	seconds.value = String(sec).padStart(2, '0')
}

onMounted(() => {
	update()
	timer = window.setInterval(update, 1000)
})

onUnmounted(() => {
	if (timer) clearInterval(timer)
})
</script>

<style scoped>
.countdown .counter {
	display: inline-flex;
	gap: 8px;
	align-items: center;
	font-weight: 600;
}
.countdown .time {
	min-width: 52px;
	text-align: center;
}
.countdown .sep {
	color: var(--text);
}
</style>

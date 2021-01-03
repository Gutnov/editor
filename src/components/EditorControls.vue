<template>
	<div class="editor-controls">
		<button class="editor-controls__item" @click="$emit('prev')">
			<Prev/>
		</button>
		<button class="editor-controls__item" @click="$emit('next')">
			<Next/>
		</button>
		<button class="editor-controls__item" @click="$emit('insert-tag', 'h2')">
			<CreateHeading/>
		</button>
		<button class="editor-controls__item" @click="$emit('insert-tag', 'h6')">
			<CreateParagraph/>
			<CreateParagraph/>
		</button>
		<button class="editor-controls__item" @click="$emit('insert-tag', 'img')">
			<InsertImage />
		</button>
		<button class="editor-controls__item" @click="$emit('copy-html')">
			Скопировать HTML
		</button>
	</div>
</template>

<script>
import CreateHeading from '@/assets/img/create-heading.svg'
import CreateParagraph from '@/assets/img/create-paragraph.svg'
import InsertImage from '@/assets/img/insert-image.svg'
import Next from '@/assets/img/next.svg'
import Prev from '@/assets/img/prev.svg'


export default {
	components: {
		CreateHeading,
		CreateParagraph,
		InsertImage,
		Next,
		Prev
	},
	methods: {
	
	},
}
</script>

<style lang="scss">
	.editor-controls {
		display: flex;
	}
	.editor-controls__item {
		display: flex;
		justify-content: center;
		align-items: center;
		min-width: 42px;
		min-height: 38px;
		margin-right: 12px;
		border-radius: 4px;
		background-color: #282828;
		transition: background-color .3s;

		&:last-child {
			background-color: transparent;
			color: #639EFF;
		}
		&:hover {
			background-color: #3f3f3f;
		}
	}
	
</style>
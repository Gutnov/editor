<template>
	<div id="app">
		<div class="editor">
			<div class="container">
				<div class="editor-controls-wr">
					<EditorControls 
						@insert-tag="insertTagHandler"
						@prev="prevHandler"
						@next="nextHandler"
						@copy-html="copyHtmlHandler"
					/>
				</div>
				<div class="editor__content" contenteditable="true" ref="editor">
					<p>
						Таким образом консультация с широким активом представляет собой интересный эксперимент проверки позиций,
						занимаемых участниками в отношении поставленных задач. С другой стороны постоянное
						информационно-пропагандистское
						обеспечение нашей деятельности представляет собой интересный эксперимент проверки форм развития. Идейные
						соображения высшего порядка, а также укрепление и развитие структуры влечет за собой процесс внедрения и
						модернизации соответствующий условий активизации. Задача организации, в особенности же реализация намеченных
						плановых заданий играет важную роль в формировании дальнейших направлений развития. Повседневная практика
						показывает, что постоянное информационно-пропагандистское обеспечение нашей деятельности играет важную роль
						в
						формировании существенных финансовых и административных условий.
					</p>
					<h2>Смотрите какие обезьянки</h2>
					<img src="@/assets/img/monkey.jpg" alt="">
					<p>
						Таким образом консультация с широким активом представляет собой интересный эксперимент проверки позиций,
						занимаемых участниками в отношении поставленных задач. С другой стороны постоянное
						информационно-пропагандистское обеспечение нашей деятельности представляет собой инйцу шо шщйоц ущойц
						ущошцщйуо йцщуо йщцоу щйоу шщйцош ущйтересный эксперимент проверки форм развития. Идейные соображения
						высшего порядка, а также укрепление и развитие структуры влечет за собой процесс внедрения и модернизации
						соответствующий условий активизации. Задача организации, в особенности же реализация намеченных плановых
						заданий играет важную роль в формировании дальнейших направлений развития. Повседневная практика показывает,
						что постоянное информационно-пропагандистское обеспечение нашей деятельности играет важную роль в
						формировании существенных финансовых и административных условий.
					</p>
					<p>
						Товарищи! новая модель организационной деятельности требуют от нас анализа направлений прогрессивного
						развития. Задача организации, в особенности же постоянный количественный рост и сфера нашей активности
						требуют от нас анализа позиций, занимаемых участниками в отношении поставленных задач. Задача организации, в
						особенности же реализация намеченных плановых заданий требуют от нас анализа системы обучения кадров,
						соответствует насущным потребностям.
					</p>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	import EditorControls from '@/components/EditorControls'

	export default {
		name: 'App',
		components: {
			EditorControls
		},
		methods: {
			insertTagHandler(tagName) {
				const selection = document.getSelection()
				if(!selection.anchorNode) return
				if(tagName === 'img') {
					console.log(document.getSelection());
					let imgSrc = prompt('Введиде путь к картинке', 'https://')
					document.execCommand('insertHTML', false, `<${tagName} src="${imgSrc}" class="content"/>`)
					return
				}
				document.execCommand('insertHTML', true, `<${tagName} class="inserted">${selection.toString()}</${tagName}>`)
			},
			prevHandler() {
				document.execCommand('undo', false, null)
			},
			nextHandler() {
				document.execCommand('redo', false, null)
			},
			copyHtmlHandler() {
				document.execCommand('copy')
			}
		}
	}
</script>

<style lang="scss">
	@import '~normalize.css/normalize.css';
	@import 'assets/scss/fonts';
	@import 'assets/scss/style';

	.editor {
		padding-top: 77px;
		padding-bottom: 107px;
	}

	.editor-controls-wr {
		margin-bottom: 31px;
	}

	.editor__content {
		outline: none;

		p {
			max-width: 621px;
			margin: 31px 0;
		}

		img {
			display: block;
			max-width: 100%;
			margin-bottom: 31px;
		}
	}
	h6.inserted {
		max-width: 621px;
		margin: 31px 0;
		font-size: 15px;
		line-height: 23px;
		font-weight: normal;
	}
</style>
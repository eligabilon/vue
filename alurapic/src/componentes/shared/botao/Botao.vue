<template>
	<button @click="disparaAcao()" class="botao botao-perigo" :type="tipo">{{ rotulo }}</button>
</template>

<script type="text/javascript">
	export default{
		props: {
			
			tipo: {
				required: true,
				type: String	
			},
			
			rotulo: {
				required:true,
				type: String
			},
			
			confirmacao: Boolean,
			estilo: String
		},

		methods:{
			disparaAcao(){
				if(confirm('Confirma operação?')){
					this.$emit('botaoAtivado', new Date());
				}
			}
		}
	}
	
</script>

<style type="text/css">
	.botao{
		display: inline-block;
		padding: 10px;
		border-radius: 3px;
		margin: 10px;
		font-size: 1.2em;
	}

	.botao-perigo{
		background: firebrick;
		color: white;		
	}

	.botao-padrao{
		background: darkcyan;
		color: white;
	}
</style>
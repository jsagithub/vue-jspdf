<template>
	<div id="home" class="container mt-5">
		<div class="row justify-content-center">
			<div class="col-md-6">
				<h1>Teste title</h1>
				<div class="card card-body">
					<div class="form-group">
						<input type="text" id="name" v-model="name" class="form-control" placeholder="Enter name here">
					</div>
					<button class="btn btn-primary pl-5 pr-5" @click="download">Download PDF</button>
				</div>
			</div>
		</div>
	</div>
</template>
<script>
	import jsPDF from 'jspdf'
	export default {
		name: 'home',
		data() {
			return {
				name: ''
			}
		},
		methods: {
			download () {
				let pdfName = 'test'; 
				var doc = new jsPDF();
				doc.fromHTML(document.getElementById('home'), 5, 5, 0, {
					'width': 170
				});
				doc.save(pdfName + '.pdf');
			}
		}
	}
</script>
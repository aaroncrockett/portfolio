<script>
	import { LightboxGallery, GalleryThumbnail, GalleryImage } from 'svelte-lightbox';

	const images = [
		{ src: 'https://picsum.photos/200/300', width: 200, height: 300 },
		{ src: 'https://picsum.photos/200/300', width: 200, height: 300 },
		{ src: 'https://picsum.photos/200/300', width: 200, height: 300 },
		{ src: 'https://picsum.photos/200/300', width: 200, height: 300 }
	];
</script>

<svelte:head>
	<title>Aaron Crockett: Artist, Designer, UI Engineer.</title>
</svelte:head>

<section>
	<h1>This website is being redesigned and developed.</h1>

	<p>images:</p>

	<LightboxGallery>
		<!-- Layout-->
		<svelte:fragment slot="thumbnail">
			<div class="sample-class-1">
				<GalleryThumbnail>
					<img src="https://picsum.photos/100/100" alt="Simple lightbox" />
				</GalleryThumbnail>
			</div>
		</svelte:fragment>

		<GalleryImage>
			<img src="https://picsum.photos/200/300" alt="Simple lightbox" />
		</GalleryImage>
		<!-- <GalleryImage>
			<img src="./image-1.jpg" alt="Simple lightbox" />
		</GalleryImage>
		<GalleryImage>
			<img src="./image-2.jpg" alt="Simple lightbox" />
		</GalleryImage> -->
	</LightboxGallery>
</section>

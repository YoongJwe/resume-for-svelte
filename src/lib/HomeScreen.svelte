<div class="home-screen">
	<img class="earth" src="earth.png" alt="earth" />
	<h1 class="title">YoongJwe's<br /> Hello World</h1>
	<div class="message">
		<p>이 페이지는 SvelteKit으로 작성되었으며, Netlify를 이용해 배포하였습니다.</p>
		<p>&copy; 2025 YoongJwe's LAB. All Rights Reserved.</p>
	</div>
</div>

<style>
	.home-screen {
		position: relative;
		top: 200px;
		display: flex;
		height: 800px;
		flex-direction: column;
		align-items: center;
	}

	.earth {
		position: absolute;
		width: 450px;
		animation:
			fadeUp 2s ease-out forwards,
			rotate 60s linear infinite;
		animation-delay: 0s, 2s;
		z-index: -1;
	}

	.title {
		position: relative;
		color: white;
		opacity: 0;
		text-align: center;
		font-size: 6rem;
		font-family: 'Henny Penny';
		animation: fadeUp 2s ease-out forwards;
		animation-delay: 2s;
		overflow-x: hidden;
		margin-bottom: 10px;
	}

	.message {
		position: relative;
		text-align: center;
		color: white;
		opacity: 0;
		font-weight: 100;
		font-family: 'Noto Sans Kr';
		font-size: small;
		animation: fadeUp 2s ease-out forwards;
		animation-delay: 3s;
	}

	@keyframes rotate {
		from {
			transform: rotate(0deg);
		}
		to {
			transform: rotate(360deg);
		}
	}

	@keyframes fadeUp {
		from {
			transform: translateY(50px);
		}
		to {
			opacity: 1;
		}
	}
</style>

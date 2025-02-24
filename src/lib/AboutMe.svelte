<script lang="ts">
	let showModal = false;
	let modalContent = '';

	function openModal(content: string) {
		modalContent = content;
		showModal = true;
	}

	function closeModal() {
		showModal = false;
	}
</script>

<div class="about-me">
	<div class="profile-container">
		<img class="profile-image" src="yoongjwe.jpg" alt="yoongjwe" />
		<div class="nickname">YoongJwe</div>
		<div class="contact">
			<button on:click={() => openModal('📱 +82 10-3065-1948')}>📱</button>
			<button on:click={() => openModal('✉️ yoongjwe@gmail.com')}>✉️</button>
		</div>
		<div class="status">
			<div>
				<sapn><span class="imoji">💼</span> 구직중 │</sapn>
				<span class="on">ON</span>
			</div>
			<div>
				<span><span class="imoji">✏️</span> 공부중 │</span>
				<span class="svelte">Svelte</span>
				<span class="swift">Swift</span>
			</div>
		</div>
	</div>
	<ul class="intro-text">
		<li>
			어릴 적부터 컴퓨터를 사용하면서 '이런 프로그램들은 대체 어떻게 만드는 걸까?' 호기심이 굉장히
			많았습니다.
		</li>
		<li>
			고등학생 때 C언어를 독학하다 혼자만의 힘으로는 조금 어려워 잠시 접고, 당장 눈 앞에 직면한 다른
			과제와 세상 사는 문제들로 인해 잊고 지냈습니다. 문득 '내가 좋아하고, 재밌게 할 수 있는 게
			뭘까?'라는 어느 날의 고찰 끝에 뒤늦게 컴퓨터공학을 시작하여 남들보다는 조금 늦게 코드를 쓰기
			시작했습니다.
		</li>
		<li>
			호기심이 많아 새로운 기술을 접하고 활용해 보는 것을 좋아하고, 컴퓨터공학과 조금이라도 관련되어
			있다면 어떤 지식이든 편식하지 않고 모두 배우고 경험해 보려고 합니다.
		</li>
		<li>
			서점에 가는 것을 좋아합니다. 서점에 놓인 수많은 서적들을 보면서 아직 이렇게나 배워야 할
			학문들이 많다는 것에 기분이 고조되고 학습에 대한 욕구가 샘솟기 때문입니다.
		</li>
	</ul>
</div>

{#if showModal}
	<div class="modal-overlay">
		<p>{modalContent}</p>
		<button on:click={closeModal} class="close-button">닫기</button>
	</div>
{/if}

<style>
	.about-me {
		position: relative;
		display: flex;
		left: 50%;
		opacity: 0;
		width: 1050px;
		height: 490px;
		background-color: white;
		border-radius: 20px;
		color: rgb(55, 55, 110);
		animation: fadeUp 2s ease-out forwards;
		animation-delay: 4s;
		margin-bottom: 50px;
		font-family: 'Noto Sans Kr';
	}

	.profile-container {
		position: relative;
		text-align: center;
		width: 300px;
		margin-left: 20px;
	}

	.profile-image {
		width: 300px;
		object-fit: cover;
		clip-path: circle(32% at 50% 37%);
		margin-bottom: -130px;
	}

	.nickname {
		font-size: 1.5rem;
		font-weight: 700;
	}

	.contact {
		font-size: 1.5rem;
		margin: 20px;
		padding: 0px 10px 3px 10px;
		background-color: ghostwhite;
		color: white;
		border-radius: 50% / 100px;
	}

	.contact button {
		all: unset;
		cursor: pointer;
	}

	.imoji {
		font-size: 1.5rem;
	}

	.on {
		padding: 0px 10px 3px 10px;
		background-color: rgb(255, 180, 0);
		color: white;
		border-radius: 50% / 25px;
		font-size: 1rem;
	}

	.svelte {
		padding: 0px 10px 3px 10px;
		background-color: rgb(255, 100, 0);
		color: white;
		border-radius: 50% / 35px;
		font-size: 1rem;
	}

	.swift {
		padding: 0px 10px 3px 10px;
		background-color: rgb(0, 120, 255);
		color: white;
		border-radius: 50% / 30px;
		font-size: 1rem;
	}

	.status {
		margin: 20px 0px 20px 30px;
		text-align: left;
		font-size: 1.2rem;
		font-weight: 600;
	}

	.modal-overlay {
		display: flex;
		flex-direction: column;
		position: fixed;
		top: 50%;
		left: 50%;
		width: 300px;
		height: 150px;
		border-radius: 10px;
		display: flex;
		text-align: center;
		align-items: center;
		justify-content: center;
		z-index: 1;
		font-family: 'Noto Sans Kr';
		font-weight: 350;
		animation: fadeUp 0.1s ease-out forwards;
		background-color: rgba(255, 255, 255, 0.9);
		border: 1px solid darkslateblue;
	}

	.close-button {
		font-family: 'Noto Sans Kr';
		font-size: 0.9rem;
		font-weight: 350;
	}

	.intro-text {
		margin: 35px 35px 0 20px;
	}

	li {
		font-size: 1.3rem;
		font-weight: 300;
		margin-bottom: 10px;
	}

	@keyframes fadeUp {
		from {
			transform: translateX(-50%) translateY(0);
		}
		to {
			opacity: 0.9;
			transform: translateX(-50%) translateY(-50px);
		}
	}
</style>

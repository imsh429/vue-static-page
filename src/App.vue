<template>
  <div class="app-wrapper">
    <!-- 헤더 / 인삿말 -->
    <header class="village-hero">
      <div class="hero-content">
        <div class="moon-emoji">🌕🐰</div>
        <h1 class="hero-title">
          반가워! 🌕 달토끼의 한가위 마을에 놀러와!
        </h1>
        <p class="hero-sub">
          풍성하고 행복한 추석을 함께 준비해요!
        </p>
      </div>

      <div class="hero-bg-card">
        <div class="village-badge">
          <span class="badge-emoji">🏡</span>
          <span class="badge-text">달토끼 마을</span>
        </div>
        <p class="hero-desc">
          오늘은 한가위를 앞둔 준비 날이에요.
          달토끼와 함께 마을을 둘러보며 도와줄 일을 찾아볼까요? 🍂
        </p>
      </div>
    </header>

    <!-- 마을 활동 섹션들 -->
    <main class="village-main">
      <!-- 활동 1 -->
      <section class="task-card">
        <div class="task-header">
          <div class="task-icon">🍡</div>
          <div class="task-info">
            <div class="task-label">활동 1</div>
            <h2 class="task-title">떡방앗간 일손 돕기</h2>
          </div>
        </div>

        <div class="task-body">
          <div class="task-body-inner">
            <div class="note-paper">
              <div class="note-pin">📌</div>
              <p class="note-title">송편 만들기</p>
              <p class="note-desc">
                송편은 오밀조밀 반달 모양으로 빚는 복을 담은 떡이에요.
                하나하나 정성스럽게 빚으면, 그만큼 복이 꽉 차서 온대요. 🐰🌕
              </p>
            </div>
          </div>
        </div>
      </section>

      <!-- 활동 2 -->
      <section class="task-card">
        <div class="task-header">
          <div class="task-icon">🍳</div>
          <div class="task-info">
            <div class="task-label">활동 2</div>
            <h2 class="task-title">풍성한 잔칫상 차리기</h2>
          </div>
        </div>

        <div class="task-body">
          <div class="task-body-inner">
            <div class="note-paper">
              <div class="note-pin">📌</div>
              <p class="note-title">전 &amp; 잡채 준비</p>
              <p class="note-desc">
                고소한 냄새가 가득!
                노릇노릇 전과 쫄깃한 잡채는
                명절 분위기를 한가득 채워주는 마법 같은 음식들이죠. 🥘✨
              </p>
            </div>
          </div>
        </div>
      </section>

      <!-- 활동 3 -->
      <section class="task-card">
        <div class="task-header">
          <div class="task-icon">🎲</div>
          <div class="task-info">
            <div class="task-label">활동 3</div>
            <h2 class="task-title">다 함께 즐거운 놀이터</h2>
          </div>
        </div>

        <div class="task-body">
          <div class="task-body-inner">
            <div class="note-paper">
              <div class="note-pin">📌</div>
              <p class="note-title">윷놀이 &amp; 강강술래</p>
              <p class="note-desc">
                다 같이 모여 웃음꽃이 활짝 피는 시간!
                윷 던지며 소리 지르고 🎉
                둥글게 손 잡고 빙글빙글 도는 강강술래까지 🌙🍂
                오늘 밤은 마을에 웃음이 가득해요.
              </p>
            </div>
          </div>
        </div>
      </section>

      <!-- 소원 나무 -->
      <section class="wish-section">
        <div class="wish-card">
          <div class="wish-header">
            <div class="wish-icon">🎀</div>
            <h2 class="wish-title">소원나무에 리본 달기</h2>
          </div>

          <p class="wish-desc">
            달토끼 소원나무에 리본을 걸면
            한가위 달빛이 살짝 비춰서 소원을 지켜준대요. 🌕🍀
          </p>

          <button class="wish-button" @click="hangWish">
            내 소원 리본 달기 🎀
          </button>

          <transition name="fade">
            <p v-if="wishPlaced" class="wish-message">
              소원이 예쁘게 걸렸어요! 꼭 이루어질 거예요. 💖
            </p>
          </transition>
        </div>
      </section>
    </main>

    <!-- 푸터 -->
    <footer class="footer">
      <p class="footer-text">
        달토끼가 전해요 🐰🌕
        “보름달만큼 마음도 가득 찬 한가위 보내세요!”
      </p>
    </footer>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const wishPlaced = ref(false)

function hangWish() {
  wishPlaced.value = true
}
</script>

<style scoped>
/* ====== 기본 색상 팔레트 ====== */
/* 배경 크림 #FFFBEB / 파스텔 peach #FFE4D6 / 파스텔 옐로우 #FFF4CC / 하늘파스텔 #EAF6FF */

.app-wrapper {
  min-height: 100vh;
  background-color: #FFFBEB; /* 따뜻한 크림색 */
  color: #4b463c;
  font-family: 'Nanum Gothic Round', 'Quicksand', 'Pretendard', system-ui,
  -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue',
  Arial, 'Noto Sans', sans-serif;
  display: flex;
  flex-direction: column;
  padding: 2rem 1rem 4rem;
  box-sizing: border-box;
}

/* ====== HERO 영역 ====== */

.village-hero {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 2rem;
  text-align: center;
}

.hero-content {
  max-width: 640px;
}

.moon-emoji {
  font-size: 2rem;
  line-height: 1;
  margin-bottom: 0.5rem;
}

.hero-title {
  font-size: clamp(1.4rem, 1.2vw, 1.6rem);
  font-weight: 700;
  color: #4b463c;
  line-height: 1.4;
  word-break: keep-all;
}

.hero-sub {
  font-size: 0.95rem;
  font-weight: 500;
  color: #6d665c;
  margin-top: 0.4rem;
  line-height: 1.5;
  word-break: keep-all;
}

.hero-bg-card {
  background: linear-gradient(
      135deg,
      rgba(255, 244, 204, 0.8) 0%,
      rgba(255, 228, 214, 0.8) 100%
  );
  border-radius: 16px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
  padding: 1rem 1.25rem;
  margin-top: 1.5rem;
  max-width: 360px;
  text-align: left;
  position: relative;
  border: 1px solid rgba(255, 255, 255, 0.6);
}

.village-badge {
  display: inline-flex;
  align-items: center;
  background-color: rgba(255, 255, 255, 0.6);
  border-radius: 12px;
  padding: 0.4rem 0.6rem;
  font-size: 0.75rem;
  font-weight: 600;
  color: #4b463c;
  box-shadow: 0 2px 6px rgba(0,0,0,0.03);
  margin-bottom: 0.5rem;
}

.badge-emoji {
  margin-right: 0.4rem;
}

.badge-text {
  line-height: 1;
}

.hero-desc {
  font-size: 0.85rem;
  color: #5a534a;
  line-height: 1.5;
  word-break: keep-all;
}

/* ====== MAIN / TASK CARDS ====== */

.village-main {
  max-width: 800px;
  width: 100%;
  margin: 0 auto;
}

/* 공통 카드 스타일 */
.task-card {
  background-color: #ffffff;
  border-radius: 20px; /* 동글동글 */
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
  border: 1px solid rgba(255, 255, 255, 0.7);
  padding: 1rem 1rem 1.25rem;
  margin-bottom: 1.5rem;
  position: relative;
}

/* 상단 영역 */
.task-header {
  display: flex;
  align-items: flex-start;
  gap: 0.75rem;
  margin-bottom: 0.75rem;
}

.task-icon {
  font-size: 1.5rem;
  line-height: 1;
  background-color: #FFF4CC; /* 연한 노랑 */
  border-radius: 12px;
  padding: 0.5rem 0.6rem;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
  border: 1px solid rgba(255,255,255,0.8);
  min-width: 2.5rem;
  text-align: center;
}

.task-info {
  display: flex;
  flex-direction: column;
}

.task-label {
  font-size: 0.7rem;
  font-weight: 600;
  color: #8a7f6d;
  background-color: #FFE4D6; /* 파스텔 피치 */
  border-radius: 8px;
  padding: 0.3rem 0.5rem;
  line-height: 1;
  box-shadow: 0 2px 6px rgba(0,0,0,0.03);
  width: fit-content;
}

.task-title {
  margin: 0.4rem 0 0 0;
  font-size: 1.05rem;
  line-height: 1.4;
  font-weight: 700;
  color: #4b463c;
  word-break: keep-all;
}

/* 본문 영역 */
.task-body {
  display: flex;
  flex-direction: column;
}

.task-body-inner {
  background-color: #EAF6FF; /* 파스텔 하늘 */
  border-radius: 16px;
  padding: 1rem;
  border: 1px solid rgba(255,255,255,0.9);
  box-shadow: 0 4px 12px rgba(0,0,0,0.03);
  position: relative;
}

/* '메모지' 느낌 */
.note-paper {
  background-color: #ffffff;
  border-radius: 16px;
  padding: 0.9rem 1rem 1rem 1rem;
  box-shadow: 0 4px 12px rgba(0,0,0,0.05);
  border: 1px solid rgba(0,0,0,0.02);
  position: relative;
  min-height: 88px;
}

.note-pin {
  position: absolute;
  top: -0.7rem;
  left: 1rem;
  font-size: 1.1rem;
  background-color: #FFE4D6;
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.07);
  border: 1px solid rgba(255,255,255,0.8);
  padding: 0.2rem 0.4rem;
  line-height: 1;
}

.note-title {
  font-size: 0.9rem;
  font-weight: 700;
  color: #4b463c;
  margin: 0 0 0.4rem 0;
  line-height: 1.4;
  word-break: keep-all;
}

.note-desc {
  font-size: 0.85rem;
  color: #5a534a;
  line-height: 1.5;
  margin: 0;
  word-break: keep-all;
  white-space: pre-line;
}

/* ====== 소원나무 섹션 ====== */

.wish-section {
  margin-top: 2rem;
  margin-bottom: 2rem;
}

.wish-card {
  background: linear-gradient(
      160deg,
      rgba(255, 255, 255, 1) 0%,
      rgba(255, 244, 204, 0.6) 100%
  );
  border-radius: 24px;
  border: 1px solid rgba(255,255,255,0.8);
  box-shadow: 0 4px 12px rgba(0,0,0,0.05);
  padding: 1.25rem 1.25rem 1.5rem;
  text-align: center;
  position: relative;
}

.wish-header {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.wish-icon {
  font-size: 1.8rem;
  line-height: 1;
  background-color: #FFE4D6;
  border-radius: 14px;
  padding: 0.5rem 0.6rem;
  border: 1px solid rgba(255,255,255,0.8);
  box-shadow: 0 4px 12px rgba(0,0,0,0.05);
  margin-bottom: 0.5rem;
}

.wish-title {
  font-size: 1.05rem;
  font-weight: 700;
  color: #4b463c;
  margin: 0;
  line-height: 1.4;
}

.wish-desc {
  font-size: 0.85rem;
  color: #5a534a;
  line-height: 1.5;
  margin: 0.75rem 0 1rem;
  word-break: keep-all;
  white-space: pre-line;
}

/* 버튼 스타일 */
.wish-button {
  background-color: #FFE4D6; /* peach */
  border: 0;
  border-radius: 16px;
  font-size: 0.9rem;
  font-weight: 600;
  padding: 0.8rem 1rem;
  line-height: 1.2;
  cursor: pointer;
  color: #4b463c;
  box-shadow: 0 4px 12px rgba(0,0,0,0.06);
  border: 1px solid rgba(255,255,255,0.8);
  transition: all 0.15s ease;
  width: 100%;
  max-width: 220px;
  margin: 0 auto;
  display: block;
}

.wish-button:hover {
  transform: translateY(-2px) scale(1.02);
  box-shadow: 0 8px 16px rgba(0,0,0,0.08);
  background-color: #ffd9c8;
}

/* 리본 메시지 */
.wish-message {
  margin-top: 1rem;
  font-size: 0.9rem;
  font-weight: 600;
  background-color: #EAF6FF;
  color: #4b463c;
  border-radius: 16px;
  padding: 0.8rem 1rem;
  border: 1px solid rgba(255,255,255,0.9);
  box-shadow: 0 4px 12px rgba(0,0,0,0.05);
  line-height: 1.4;
  word-break: keep-all;
  white-space: pre-line;
}

/* 페이드 인/아웃 트랜지션 */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.2s ease, transform 0.2s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
  transform: translateY(4px);
}

/* ====== FOOTER ====== */

.footer {
  text-align: center;
  margin-top: auto;
  padding-top: 2rem;
  font-size: 0.8rem;
  color: #6d665c;
  line-height: 1.5;
  word-break: keep-all;
}

.footer-text {
  background-color: rgba(255,255,255,0.6);
  display: inline-block;
  padding: 0.9rem 1rem;
  border-radius: 16px;
  border: 1px solid rgba(255,255,255,0.8);
  box-shadow: 0 4px 12px rgba(0,0,0,0.05);
  max-width: 320px;
  white-space: pre-line;
}

/* ====== 반응형 ====== */

@media (min-width: 480px) {
  .hero-title {
    font-size: 1.6rem;
  }
  .hero-sub {
    font-size: 1rem;
  }
  .task-title {
    font-size: 1.1rem;
  }
  .wish-title {
    font-size: 1.1rem;
  }
  .wish-button {
    font-size: 1rem;
  }
}

@media (min-width: 640px) {
  .village-hero {
    margin-bottom: 2.5rem;
  }

  .hero-bg-card {
    max-width: 400px;
  }

  .task-card {
    padding: 1.25rem 1.25rem 1.5rem;
  }
  .task-header {
    gap: 1rem;
  }
  .task-icon {
    font-size: 1.6rem;
    min-width: 2.8rem;
  }

  .task-body-inner {
    padding: 1.25rem;
  }

  .note-paper {
    padding: 1rem 1rem 1.1rem;
    min-height: 96px;
  }
  .note-title {
    font-size: 1rem;
  }
  .note-desc {
    font-size: 0.9rem;
  }

  .wish-card {
    padding: 1.5rem 1.5rem 1.75rem;
  }
}
</style>

<!--
필요한 추가 사항:
1. index.html 쪽에
   <link rel="preconnect" href="https://fonts.gstatic.com" />
   <link href="https://fonts.googleapis.com/css2?family=Nanum+Gothic+Round:wght@400;500;700&family=Quicksand:wght@400;500;600;700&display=swap" rel="stylesheet">
   넣어주면 폰트 적용돼요.

2. 이 파일은 src/App.vue 로 저장하면 됩니다.
-->

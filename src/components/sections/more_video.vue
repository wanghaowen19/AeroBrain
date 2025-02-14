<script setup>
import { onMounted } from "vue";

const BASE_URL = "/AeroBrain";  // 添加子路径，适配 GitHub Pages

const videos = [
  { src: `${BASE_URL}/video/video_final/Find_extinguisher_1.mp4`, title: "Find a fire extinguisher" },
  { src: `${BASE_URL}/video/video_final/Find_Cone_record_1.mp4`, title: "Find a cone" },
  { src: `${BASE_URL}/video/video_final/Find_elerecord_1.mp4`, title: "Find an electrical Panel" },
  { src: `${BASE_URL}/video/video_final/Find_telephone_1.mp4`, title: "Find a telephone on the table" },
  { src: `${BASE_URL}/video/video_final/Find_pipes_1.mp4`, title: "Find some plastic pipes on the shelf" },
  { src: `${BASE_URL}/video/video_final/Find_fence_1.mp4`, title: "Find a fence" }
];

// 确保路径正确解析
function getVideoUrl(src) {
  return `${window.location.origin}${src}`;
}

// 页面加载后强制刷新视频，确保 Vue 正确加载
onMounted(() => {
  document.querySelectorAll("video").forEach(video => {
    video.load(); // 强制重新加载视频，避免 Vue 组件渲染导致无法播放
  });
});

// 监听视频加载错误
function handleVideoError(event, title) {
  console.error(`Error loading video: ${title} - URL: ${event.target.currentSrc}`);
  event.target.outerHTML = `<p style="color:red; text-align:center;">Failed to load video: ${title}</p>`;
}
</script>

<template>
  <div>
    <el-divider />
    <el-row justify="center">
      <h1 class="section-title">More Video Demos</h1>
    </el-row>
    <el-row justify="center">
      <el-col :xs="24" :sm="20" :md="16" :lg="12" :xl="12">
        <el-row :gutter="20" justify="center">
          <el-col v-for="(video, index) in videos" :key="index" :xs="24" :sm="20" :md="16" :lg="12" :xl="12">
            <div class="video-wrapper">
              <video 
                controls 
                muted 
                preload="auto" 
                playsinline
                @error="handleVideoError($event, video.title)">
                <source v-bind:src="getVideoUrl(video.src)" type="video/mp4" />
              </video>
              <h3 class="video-title">{{ video.title }}</h3>
            </div>
          </el-col>
        </el-row>
      </el-col>
    </el-row>
  </div>
</template>

<style scoped>
.video-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  margin: 20px 0;
}

.video-title {
  margin-top: 10px;
  font-size: 16px;
  font-weight: bold;
}

video {
  width: 100%;
  max-width: 100%;
  aspect-ratio: 16 / 9;
  background-color: black;
}
</style>

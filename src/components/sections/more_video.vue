<script setup>
import { onMounted } from "vue";

const videos = [
  { src: "/video/video_final/Find_extinguisher_1.mp4", title: "Find a fire extinguisher" },
  { src: "/video/video_final/Find_Cone_record_1.mp4", title: "Find a cone" },
  { src: "/video/video_final/Find_elerecord_1.mp4", title: "Find an electrical Panel" },
  { src: "/video/video_final/Find_telephone_1.mp4", title: "Find a telephone on the table" },
  { src: "/video/video_final/Find_pipes_1.mp4", title: "Find some plastic pipes on the shelf" },
  { src: "/video/video_final/Find_fence_1.mp4", title: "Find a fence" }
];

// 确保视频路径完整
function getVideoUrl(src) {
  return `${window.location.origin}${src}`;
}

// 页面加载后强制刷新视频
onMounted(() => {
  document.querySelectorAll("video").forEach(video => {
    video.load(); // 强制重新加载视频
  });
});

// 监听视频错误
function handleVideoError(event, title) {
  console.error(`Error loading video: ${title}`);
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
              <p>{{ getVideoUrl(video.src) }}</p> <!-- 打印路径，确保 Vue 正确解析 -->
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

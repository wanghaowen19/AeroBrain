<script setup>
const videos = [
  { src: "/video/video_final/Find_extinguisher_1.mp4", title: "Find a fire extinguisher" },
  { src: "/video/video_final/Find_Cone_record_1.mp4", title: "Find a cone" },
  { src: "/video/video_final/Find_elerecord_1.mp4", title: "Find an electrical Panel" },
  { src: "/video/video_final/Find_telephone_1.mp4", title: "Find a telephone on the table" },
  { src: "/video/video_final/Find_pipes_1.mp4", title: "Find some plastic pipes on the shelf" },
  { src: "/video/video_final/Find_fence_1.mp4", title: "Find a fence" }
];
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
                preload="metadata" 
                playsinline
                :onerror="(event) => handleVideoError(event, video.title)">
                <source :src="video.src" type="video/mp4" />
                Your browser does not support the video tag.
              </video>
              <h3 class="video-title">{{ video.title }}</h3>
            </div>
          </el-col>
        </el-row>
      </el-col>
    </el-row>
  </div>
</template>

<script>
function handleVideoError(event, title) {
  console.error(`Error loading video: ${title}`);
  event.target.outerHTML = `<p style="color:red; text-align:center;">Failed to load video: ${title}</p>`;
}
</script>

<style scoped>
.video-wrapper {
  display: flex;
  flex-direction: column; /* 确保视频和标题垂直排列 */
  align-items: center; /* 让内容居中 */
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
  max-width: 100%; /* 确保视频不会超出容器 */
  aspect-ratio: 16 / 9;
  background-color: black; /* 避免加载失败时黑屏 */
}
</style>

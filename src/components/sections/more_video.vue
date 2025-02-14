<script setup>
const videos = [
  { src: "/public/video/video_final/Find_extinguisher_1.mp4", title: "Find a fire extinguisher" },
  { src: "/public/video/video_final/Find_Cone_record_1.mp4", title: "Find a cone" },
  { src: "/public/video/video_final/Find_elerecord_1.mp4", title: "Find an electrical Panel" },
  { src: "/public/video/video_final/Find_telephone_1.mp4", title: "Find a telephone on the table" },
  { src: "/public/video/video_final/Find_pipes_1.mp4", title: "Find some plastic pipes on the shelf" },
  { src: "/public/video/video_final/Find_fence_1.mp4", title: "Find a fence" }
];

function getVideoUrl(src) {
  return `${window.location.origin}${src}`; // 确保是完整路径
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
                preload="metadata" 
                playsinline 
                :onerror="(event) => handleVideoError(event, video.title)">
                <source :src="getVideoUrl(video.src)" type="video/mp4" />
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

<template>
    <div class="video-container">
      <video src="../static/video/20230630_134035.mp4" id="my-video"></video>
      <button class="play-button" id="play-button"></button>
    </div>
  </template>
  
  <style lang="scss" scoped>
  .video-container {
    position: relative;
    width: 100%;
    height: 0;
    padding-bottom: 56.25%; /* 设置视频容器的高度为宽度的16:9比例，根据需要进行调整 */
  }
  
  #my-video {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }
  
  .play-button {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 80px; /* 设置按钮宽度 */
    height: 80px; /* 设置按钮高度 */
    background-color: rgba(0, 0, 0, 0.5); /* 设置按钮背景颜色，根据需要进行调整 */
    border-radius: 50%; /* 设置按钮为圆形 */
    border: none; /* 去除按钮边框 */
    outline: none; /* 去除按钮点击时的虚线边框 */
    cursor: pointer;
  }
  
  .play-button:before {
    content: ""; /* 使用伪元素创建按钮中间的三角形图标 */
    position: absolute;
    top: 50%;
    left: 50%; /* 调整三角形在按钮中的位置 */
    transform: translate(-50%, -40%);
    width: 0;
    height: 0;
    border-left: 18px solid #fff; /* 设置三角形的颜色和大小，根据需要进行调整 */
    border-top: 12px solid transparent;
    border-bottom: 12px solid transparent;
  }
  
  .play-button:hover {
    background-color: rgba(0, 0, 0, 0.8); /* 设置按钮在鼠标悬停时的背景颜色，根据需要进行调整 */
  }
  </style>
  
  <script>
  export default {
    mounted() {
      const video = document.getElementById('my-video');
      const playButton = document.getElementById('play-button');
      
      playButton.addEventListener('click', () => {
        if (video.paused) {
          video.play();
          playButton.style.display = 'none'; // 播放时隐藏按钮
        } else {
          video.pause();
          playButton.style.display = 'block'; // 暂停时显示按钮
        }
      });
    }
  }
  </script>
  
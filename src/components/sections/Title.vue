<script lang="ts" setup>

import { ElIcon } from 'element-plus'
import { Document, Files, MagicStick, Picture, DataAnalysis, Film } from '@element-plus/icons-vue'

// logo地址，没有则置为""即可
const logo = ''

// 标题
const title = 'AeroBrain:  Multimodal Large-Model and Deep Reinforcement Learning-Powered UAV Navigation for Natural Language Object Search'

// 标题颜色
const title_color = '#000000'

// 标题补充，没有则置为''即可
const title_supp = ''

// 标题补充颜色
const title_supp_color = '#42B883'

// 按钮颜色
const btn_color = '#444444'

// 作者清单（包含作者姓名、头像、主页、地址序号）
const authors = [
  {
    name: "Haowen Wang",
    icon: "",
    homepage: "",
    address_flag: "1"
  },
  {
    name: "Junyu Wei",
    icon: "",
    homepage: "",
    address_flag: "2"
  },
  {
    name: "Jiangyi Qin",
    icon: "",
    homepage: "",
    address_flag: "3"
  },
  {
    name: "Ni Zhu",
    icon: "",
    homepage: "",
    address_flag: "4"
  },
  {
    name: "Zongqing Zhao",
    icon: "",
    homepage: "",
    address_flag: "2"
  },
  {
    name: "Zhuoyuan Wu",
    icon: "",
    homepage: "",
    address_flag: "2"
  },
  {
    name: "Shiqi Li",
    icon: "",
    homepage: "",
    address_flag: "2"
  },
  {
    name: "Zhiqiang Wang",
    icon: "",
    homepage: "",
    address_flag: "5"
  }
]

// 地址清单（包含地址名称、头像、主页、地址序号）
const addresses = [
  // {
  //   address_flag: "1",
  //   name: "Peking University",
  //   icon: "./icon/home.png",
  //   homepage: "https://github.com/hmuniversity"
  // },
  // {
  //   address_flag: "2",
  //   name: "IKUN University",
  //   icon: "./icon/ikun.avif",
  //   homepage: "https://www.bilibili.com/video/BV178411Y7QB"
  // },
]

// 共一和通讯提示
const con_and_corresponding_author = 
  ""

const school1 = 
  "1 School of Electronic, Peking University, Beijing, China."

const school2 = 
  "2 College of	Intelligence Science and Technology, National University of Defense Technology, Changsha, China."

  const school3 = 
  "3 National Innovation Institute of Defense Technology	Academy of Military Science, Beijing, China."

  const school4 = 
  "4 AME-GEOLOC, Université Gustave Eiffel, Pairs, France"

  const school5 = 
  "5 Leonard de Vinci Graduate School of Engineering, Pairs, France"

  const notice = 
  "🚀 Noitice: This work has been submitted to IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS) "

  
// 最新消息
const news = "🔥 [2024-12-15] This template project is still under development."

// 强调内容
// const emphases = ["🚀 Noitice: This work has been submitted to 2025 IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS)"
// ]

const emphases = ["🚀 Noitice: This work has been submitted to 2025 IROS"
]

// 提供引导资料链接
const buttons = [
  // {
  //   disabled: true,
  //   name: "Paper",
  //   component: Document,
  // },
  // {
  //   disabled: true,
  //   name: "中译版",
  //   component: Document,
  // },
  // {
  //   disabled: false,
  //   name: "Code",
  //   link: "https://github.com/JunyaoHu/academic-project-page-template-vue",
  //   component: Files,
  // },
  {
    disabled: false,
    name: "Demo",
    link: "https://junyaohu.github.io/academic-project-page-template-vue",
    component: MagicStick,
  },
  // {
  //   disabled: true,
  //   name: "Poster",
  //   component: Picture,
  // },
  // {
  //   disabled: true,
  //   name: "Slide",
  //   component: DataAnalysis,
  // },
  // {
  //   disabled: false,
  //   name: "Video (减论)",
  //   link: "https://www.bilibili.com/video/BV15XkgYiE73/",
  //   component: Film,
  // },
  // {
  //   disabled: false,
  //   name: "Video (Tutorial)",
  //   link: "https://www.bilibili.com/video/BV1oUrfYzEqZ",
  //   component: Film,
  // },
]

</script>

<template>
  <div>

    <!-- 最新消息提示
    <el-row justify="center">
      <el-col :span="24">
        <el-alert title="🔥 This template is still under development." type="success" />
      </el-col>
    </el-row> -->

    <!-- 文章logo -->
    <el-row v-if="logo" justify="center">
      <el-image :src="logo" class="logo" fit="cover" />
    </el-row>

    <!-- 文章标题 -->
    <el-row justify="center">
      <el-col :span="20">
        <h1 class="paper-title">
          <span v-if="title" :style="{color:title_color}"> {{ title }}</span>
          <span v-if="title_supp" :style="{color:title_supp_color}"> {{ title_supp }}</span>
        </h1>
      </el-col>
    </el-row>

    <!-- 作者名单 -->
    <!-- <el-row justify="center">
      <a :href=author.homepage v-for="author in authors">
        <el-button class="title-button" type="primary" text>
          <el-avatar v-if="author.icon" :size="40" :src="author.icon" />
          <span class="author">
            {{ author.name }}<sup v-if="author.address_flag" class="name_sup">{{ author.address_flag }}</sup>
          </span>
        </el-button>
      </a>
    </el-row> -->

    <el-row justify="center">
    <el-button
      v-for="author in authors"
      :key="author.name"
      class="title-button no-hover-effect"
      type="primary"
      text
    >
      <el-avatar v-if="author.icon" :size="40" :src="author.icon" />
      <span class="author">
        {{ author.name }}
        <sup v-if="author.address_flag" class="name_sup">{{ author.address_flag }}</sup>
      </span>
    </el-button>
  </el-row>


    <!-- 地址名单 -->
    <el-row justify="center">
      <a :href=address.homepage v-for="address in addresses">
        <el-button class="title-button" type="primary" text>
          <el-avatar v-if="address.icon" :size="40" :src="address.icon" />
          <span class="address">
            <sup v-if="address.address_flag" class="address_sup">{{ address.address_flag }}</sup>{{ address.name }}
          </span>
        </el-button>
      </a>
    </el-row>

    <!-- 共一和通讯提示内容 -->
    <!-- <el-row justify="center" class="con-cor">
        {{ con_and_corresponding_author }}
    </el-row> -->

    <el-row justify="center" class="con-cor">
        {{ school1 }}
    </el-row>
    <el-row justify="center" class="con-cor">
        {{ school2 }}
    </el-row>
    <el-row justify="center" class="con-cor">
        {{ school3 }}
    </el-row>
    <el-row justify="center" class="con-cor">
        {{ school4 }}
    </el-row>
    <el-row justify="center" class="con-cor">
        {{ school5 }}
    </el-row>
    <!-- <el-row justify="center" class="con-cor">
        {{ notice }}
    </el-row> -->
    <!-- 强调内容 -->
    <el-row justify="center" class="emphasis" v-for="emphasis in emphases">
        {{ emphasis }}
    </el-row>

    <!-- 提供引导按钮 -->
    <!-- <el-row justify="center" style="margin-bottom: 20px;">
      <el-col :span="20">
        <el-row justify="center">
          <a :href=button.link v-for="button in buttons">
            <el-button class="guidance-button" size="default" :color="btn_color" :disabled="button.disabled" round>
              <el-icon :size="18">
                <component :is="button.component" />
              </el-icon>
              <span class="btn-text">{{ button.name }}</span>
            </el-button>
          </a>
        </el-row>
      </el-col>
    </el-row> -->

  </div>
</template>

<style scoped>

/* 文章标题字体、字间距、居中排布、字号 */
.paper-title {
  font-family: "MyFont", Verdana, sans-serif;
  letter-spacing: 2px;
  font-size: 42px;
  margin: 32px;
  text-align: center;
}

/* 姓名和地址按钮 */
.title-button {
  margin: 10px 3px;
  border: none; /* 移除边框 */
  box-shadow: none; /* 移除阴影 */
}

/* 取消悬浮时的边框和阴影 */
.title-button:hover {
  margin: 10px 3px; 
  border: none;
  box-shadow: none;
}

/* 取消特殊的 hover 效果 */
.no-hover-effect {
  text-decoration: none;
  color: inherit;
  cursor: default;
  border: none;
  box-shadow: none;
}

.no-hover-effect:hover {
  text-decoration: none;
  color: inherit;
  cursor: default;
  border: none;
  box-shadow: none;
}

/* 全局覆盖 el-button 悬停时的边框 */
.el-button:hover {
  border: none !important; /* 强制去掉边框 */
  box-shadow: none !important; /* 强制去掉阴影 */
}

/* 引导材料按钮 */
.guidance-button {
  margin: 8px 5px;
  box-shadow: #d8d8d8 1px 1px 1px 1px;
}

/* 姓名属性 */
.author {
  font-size: 18px;
  margin-left: 3px;
}

/* 姓名上标属性 */
.name_sup {
  color: #606266; 
  margin-left: 3px;
}

/* 地址属性 */
.address {
  font-size: 18px;
}

/* 地址上标属性 */
.address_sup {
  color: #606266; 
  margin-right: 1px;
}

/* 头像属性 */
.el-avatar {
  margin-right: 6px;
  box-shadow: #b7b7b7 0px 0px 3px 1px;
}

/* 共一和通讯文字属性 */
.con-cor {
  /* font-family: Arial; */
  font-size: 14px;
  margin: 18px 0px;
  text-align: center;
}

/* 强调信息属性 */
.emphasis {
  color: chocolate;
  font-weight: bold;
  margin: 8px;
  font-size: 22px;
  text-align: center;
}

/* 引导材料按钮文字属性 */
.btn-text {
  font-size: 18px;
  color: #ffffff;
}

.el-alert {
  margin: 10px 0 0;
}

.el-alert:first-child {
  margin: 0;
}

.logo {
  width: 150px; 
  height: 150px;
  border-radius: 50%;
  box-shadow: #ced3dc 0px 0px 3px 2px;
  margin-top: 40px;
}

/* 手机端链接样式处理 */
a:-webkit-any-link {
  text-decoration: none;
}

/* 取消鼠标焦点悬浮在链接上的颜色装饰 */
a:hover {
  color: inherit;
  border-bottom: none;
}

/* 链接装饰，取消下划线和链接颜色 */
a {
	text-decoration: None;
	color: inherit;
}

/* 仅作用于特定名字，禁止悬停时的变化 */
.no-hover-effect {
  text-decoration: none;
  color: inherit;
  cursor: default;
  border: none !important;
  box-shadow: none !important;
}

.no-hover-effect:hover {
  text-decoration: none;
  color: inherit;
  cursor: default;
  border: none !important;
  box-shadow: none !important;
}

</style>
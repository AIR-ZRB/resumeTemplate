<template>
  <div id="app">
    <div class="container">
      <header>
        <h1 :style="{ borderColor: themeColor }">个人简历</h1>
        <section>
          <p>求职意向：前端工程师</p>
          <p>Personal resume</p>
        </section>
      </header>

      <main>
        <div class="left-column">
          <section class="personal-message">
            <Title title="基本信息"></Title>
            <ul>
              <li v-for="item in message" :key="item.type">
                <img :src="require('./assets/' + item.type + '.png')" alt="" />
                {{ item.value }}
              </li>
            </ul>
          </section>

          <section class="skill">
            <Title title="掌握技能"></Title>
            <ul>
              <li v-for="item in skill" :key="item">{{ item }}</li>
            </ul>
          </section>

          <section class="skill-picture">
            <Title title="技能图谱"></Title>
            <ul>
              <li v-for="item in skillPicture" :key="item.name">
                <p>{{ item.name }}</p>
                <p>
                 
                  <span :style="{ width: item.percentage }"></span>
                </p>
              </li>
            </ul>
          </section>
        </div>

        <div class="right-column">
          <section>
            <Title title="项目经验"></Title>
            <dl>
              <dt>移动端记账软件（未完成）</dt>
              <dd>使用技术：vue，vuex，vue-router，cordova，sass，webpack</dd>
              <dd>
                项目描述：灵感来源于叨叨记账，能够对每日的消费进行输入记录，能够看到每个月的花销情况，
              </dd>
              <dd>
                项目分析：使用了cordova来操作文件系统，能够让数据保存，使用vue-router来进行路由的跳转，使用vuex来对之间的传值，使用webpack对项目进行打包优化
              </dd>
              <dd><a href="">点击预览</a></dd>
            </dl>
          </section>
        </div>
      </main>
    </div>
  </div>
</template>

<script>
import Title from "./components/Title";
export default {
  name: "App",
  data() {
    return {
      name: "zrb",
      message: [
        { type: "phone", value: "15889580759" },
        { type: "weChat", value: "15889580759" },
        { type: "email", value: "1057605824@qq.com" },
        { type: "education", value: "大专" }
      ],
      skill: [
        "掌握HTML5/CSS3，熟悉传统布局、Flex布局、Grid布局、移动端适配等",
        "熟悉Vue技术栈如Vue-Router、Vuex、Vue-CLI及相关流行库的使用，理解其重要概念",
        "熟悉React / Redux技术栈等使用，能够使用React进行基本开发",
        "熟悉前后端交互技术JSONP、AJAX，了解fetch",
        "熟悉Node.js开发，能搭建基础后台开发"
      ],
      skillPicture: [
        { name: "JavaScript", percentage: "50%" },
        { name: "Node", percentage: "50%" },
        { name: "CSS3", percentage: "80%" },
        { name: "Vue", percentage: "60%" },
        { name: "React", percentage: "75%" }
      ],
      themeColor: "#1ACABD"
    };
  },
  components: {
    Title
  }
};
</script>

<style lang="scss">
$themeColor: #1acabd;
$space: 50px;

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.container {
  width: 1200px;
  height: 700px;
  margin: 0 auto;

  header {
    display: flex;
    align-items: center;
    height: 100px;
    color: $themeColor;
    position: relative;

    h1 {
      border-right: 3px solid #ccc;
      padding: 0 20px 0 0;
    }

    section {
      margin: 0 0 0 20px;
      p:last-child {
        font-size: 22px;
      }
    }

    &::before {
      content: "";
      width: 70%;
      height: 30px;
      background: $themeColor;
      position: absolute;
      bottom: -20px;
    }

    &::after {
      content: "";
      width: 30%;
      height: 30px;
      background: #111;
      position: absolute;
      right: 0;
      bottom: -20px;
    }
  }

  main {
    margin-top: 50px;
    width: 100%;
    height: 100%;
    display: grid;
    grid-template-columns: 30% 70%;

    section {
      margin-bottom: $space;
    }

    .left-column {
      .personal-message {
        li {
          list-style: none;
          height: 30px;
          line-height: 30px;
          img {
            width: 20px;
            height: 20px;
          }
        }
      }

      .skill {
        ul {
          padding-left: 30px;
          li {
            margin-bottom: 10px;
          }
        }
      }

      .skill-picture {
        ul {
          li {
            list-style: none;

            p {
              width: 100%;
			  line-height: 40px;

              &:last-child {
                height: 10px;
				border-radius: 5px;
                background: #ccc;
				span {
					float: left;
					height: 100%;
					background: $themeColor;
				}
              }
            }
          }
        }
      }
    }

    .right-column {
      padding-left: 100px;
      //   background: blue;
    }
  }
}

.height-light {
  color: red;
}
</style>

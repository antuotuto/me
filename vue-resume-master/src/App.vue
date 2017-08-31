<template>
  <div id="app">
    <div class="resume">
      <div class="left">
        <Brief></Brief>
        <ContextList title="联系方式" :icon="require('@/assets/title-contact.png')">
          <ListItemInfo title="17610705501"
                        :image="require('@/assets/contact-phone.png')"
                        slot="listItem">
          </ListItemInfo>
          <ListItemInfo title="675988829@qq.com"
                        :image="require('@/assets/contact-mail.png')"
                        slot="listItem">
          </ListItemInfo>
          <ListItemInfo title="antuotuo2016"
                        :image="require('@/assets/social-wechat.png')"
                        slot="listItem">
          </ListItemInfo>
          <ListItemInfo title="675988829"
                        :image="require('@/assets/social-qq.png')"
                        slot="listItem">
          </ListItemInfo>
        </ContextList>
        <ContextList title="社交网站" :icon="require('@/assets/title-contact.png')">
          <ListItemInfo title="https://github.com/antuotuto"
                        :image="require('@/assets/social-github.png')"
                        slot="listItem">
          </ListItemInfo>
        </ContextList>
      </div>
      <div class="right">
        <ContextList title="关于">
          <ListItemAbout slot="listItem"></ListItemAbout>
        </ContextList>
        <ContextList title="技术展示">

        </ContextList>
        <div class="about-me">
          <a href="https://antuotuto.github.io/About-Lover/#/home/1" target="_blank">
            个人博客
          </a>
          <a href="http://118.89.203.41/" target="_blank">
            后台管理系统
          </a>
        </div>
        <ContextList title="技能">
          <ListItemSkill slot="listItem" title="JavaScript" :percent="70"></ListItemSkill>
          <ListItemSkill slot="listItem" title="Html5 + css3" :percent="80"></ListItemSkill>
          <ListItemSkill slot="listItem" title="Vue" :percent="70"></ListItemSkill>
        </ContextList>
        <ContextList title="教育">
          <ListItemEducation slot="listItem" school="湖南中医药大学" major="" date="2013.9 — 2015.7"></ListItemEducation>
        </ContextList>
        <ContextList title="经历">
          <ListItemExperience slot="listItem" job="十二药网系统重构项目" company="十二药网" date="2015.6 - 2015.12" text="本人职责,Web前端工程师,团队人数,大于15人,工作内容，编写十二药网前台页面，主要是广告页，用到的技术是基础的html，和css。"></ListItemExperience>
          <ListItemExperience slot="listItem" job="药批发网后台" company="药批发网" date="2015.12 - 2016.3" text="本人职责,Web前端工程师,团队人数,大于15人,工作内容，药批发网的用户管理和个人中心的页面编写，在用html和css的同时加入了easyui。"></ListItemExperience>
          <ListItemExperience slot="listItem" job="海南残联项目" company="财资易通" date="2016.4 - 2016.7" text="本人职责,Web前端工程师,团队人数,大于20人,工作内容，使用Bootstrap开发的后台系统。"></ListItemExperience>
          <ListItemExperience slot="listItem" job="重庆金融云跨境资金管理平台" company="财资易通" date="2016.7 - 2017.8" text="本人职责,Web前端工程师,团队人数,大于20人,工作内容使用vue.js，element开发重庆金融云跨境资金管理平台。"></ListItemExperience>
        </ContextList>
      </div>
    </div>
    <div class="guide">
      <ul>
        <li>
          <img src="./assets/guide_click_left.png" height="60" width="60" alt="">
          <div class="desc">
            <h3>点击为选项卡</h3>
          </div>
        </li>
        <li>
          <img src="./assets/guide_click_right.png" height="60" width="60" alt="">
          <div class="desc">
            <h3>三击复制文字内容</h3>
          </div>
        </li>
      </ul>
    </div>
    <button class="sap" @click="saveAsImage">保存为图片</button>
    <div class="footer">
      <a href="https://github.com/antuotuto" target="_blank">
        <img src="./assets/social-github.png" height="36" width="36" alt="">
      </a>
       Designed by <a href="https://github.com/antuotuto">王安安</a>
    </div>
  </div>
</template>

<script>
import ContextList from '@/components/context-list'
import ListItemAbout from '@/components/list-item-about'
import ListItemSkill from '@/components/list-item-skill'
import ListItemEducation from '@/components/list-item-education'
import ListItemExperience from '@/components/list-item-experience'
import ListItemInfo from '@/components/list-item-info'
import html2canvas from '@/assets/js/html2canvas.js'
import FileSaver from 'file-saver'
import Brief from '@/components/brief'

export default {
  name: 'app',
  components: {
    ContextList,
    ListItemAbout,
    ListItemSkill,
    ListItemEducation,
    ListItemExperience,
    ListItemInfo,
    Brief
  },
  methods: {
    saveAsImage: function () {
      let resume = document.querySelector('.resume')
      html2canvas(resume).then(function (canvas) {
        canvas.toBlob(function (blob) {
          FileSaver.saveAs(blob, 'Resume.png')
        })
      })
    }
  }
}
</script>

<style lang="less">
  body{
    padding: 0;
    margin: 0;
  }
  ul{
    padding: 0;
    margin: 0;
    li{
      list-style: none;
    }
  }
  p{
    margin: 0 0 12px 0;
  }
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: left;
    color: #2c3e50;
    background-color: white;
    display: flex;
    flex-direction:column;
    align-items: center;
    justify-content: center;
    padding: 40px 0;
    .resume{
      width: 1247px;
      height: 1754px;
      border: 1px solid #dad8d7;
      background-color: white;
      overflow: hidden;
      .left{
        width: 380px;
        height: 100%;
        box-sizing: border-box;
        float: left;
        background-color: #fdfefe;
        .brief{
          height: 630px;
          background-color: #f6f7f7;
          .avatar{
            height: 500px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            &>.img{
              margin-bottom: 45px;
            }
            .name{
              font-size: 32px;
              margin-bottom: 14px;
            }
            .job{
              font-size: 24px;
              color: #555;
              margin-bottom: 16px;
            }
            .location{
              display: flex;
              align-itmes: center;
              .location-name{
                font-size: 20px;
                font-weight: bold;
                margin-left: 10px;
              }
            }
          }
          .info{
            height: 128px;
            ul{
              height: 100%;
              display: flex;
              border-top: 1px solid #dad8d7;
              border-bottom: 1px solid #dad8d7;
              li:not(:last-child){
                border-right: 1px solid #dad8d7;
              }
              li{
                width: 33.3333333%;
                display: flex;
                flex-direction: column;
                justify-content: center;
                text-align: center;
                .value{
                  margin-bottom: 10px;
                  font-size: 24px;
                  font-weight: bold;
                }
                .key{
                  font-size: 16px;
                  font-weight: bold;
                  color: #555;
                }
              }
            }
          }
        }
      }
      .right{
        box-sizing: border-box;
        width: 867px;
        float: left;
        padding: 50px 40px;
        p{
          font-size: 20px;
          line-height: 32px;
          color: #555;
          text-align:justify;
        }
      }

    }
    button.sap{
      position: absolute;
      top: 65px;
      left: 50%;
      margin-left: 478px;
      background-color: white;
      border: 1px solid #dad8d7;
      cursor: pointer;
      padding: 5px 8px;
      border-radius: 4px;
      &:hover{
        background-color: #f8f8f8;
      }
    }
    .guide{
      border: 1px solid #dad8d7;
      width: 1247px;
      margin-top: 15px;
      height: 120px;
      ul{
        width: 100%;
        height: 100%;
        display: flex;
        justify-content: space-around;
        align-items: center;
        li{
          display: flex;
          align-items: center;
          img{
            margin: 0 10px;
          }
          h3{
            margin: 0 0 6px 0;
          }
          p{
            margin: 0;
            font-size: 16px;
          }
        }
      }
    }
    .footer{
      line-height: 50px;
      a{
        text-decoration: none;
        color: #4aa74f;
        &:first-child{
          display: block;
          text-align: center;
          line-height: 0;
          margin-top: 15px;
        }
      }
    }
  }

  .about-me{
    padding-bottom: 15px;
    margin-top: -15px;
    a{
      display: inline-block;
      padding: 0.3em 0.9em;
      margin: 0 0.5em 0.5em 0;
      white-space: nowrap;
      background-color: #f1f8ff;
      border-radius: 3px;
      color: #0366d6;
      text-decoration: none;
      font-size: 12px ;
      padding: 10px;
    }
  }

</style>

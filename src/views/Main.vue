<template>
    <div id="app" style="height: 100%;">
        <div id="resume" class="container" style="height: 100%;">
            <!--基础信息-->
            <section class="row" style="width: 100%;height: 295px;">
                <div class="col" style="width: 18rem;">
                  <div style=" display: table-cell; text-align: center;vertical-align: middle;">
                      <img v-bind:src="img" class="one" style="width: 180px; height: 180px; border-radius: 50%;">
                  </div>
                  <div class="card-body">
                    <p class="card-text">{{ personinfo }}</p>
                    <p class="card-text">{{ personextra }}</p>
                  </div>
                </div>
                <div class="col" style="">
                    <div style="margin-top: 5px">
                        <el-tag>姓名</el-tag>
                        <i class="el-icon-user-solid" style="height: 100%;">{{name}}</i></div>
                    <div style="margin-top: 5px">
                        <el-tag>求职意向</el-tag>
                        <i class="el-icon-warning" style="height: 100%;">{{job}}</i></div>
                    <div style="margin-top: 5px;">
                        <el-tag>电话</el-tag>
                        <i class="el-icon-star-on">{{phone}}</i>
                    </div>

                    <div style="margin-top: 5px">
                        <el-tag>邮箱</el-tag>
                        <i class="el-icon-s-finance" style="height: 100%;"> {{email}}</i>
                    </div>

                    <div style="margin-top: 5px">
                        <el-tag>Github</el-tag>
                        <i class="el-icon-s-home" style="height: 100%;"><a v-bind:href=github>{{github}}</a></i>
                    </div>
                    <div style="margin-top: 5px">
                        <el-tag>博客</el-tag>
                        <i class="el-icon-s-order" style="height: 100%;"><a v-bind:href=blog>{{blog}}</a></i>
                    </div>
                </div>
            </section>

            <!--教育背景-->
            <div class="education " style="margin-top: 30px;">
               <h2><span class="badge badge-info">{{education_ba}}</span></h2>
                <hr style="border-top: 1px solid #161515; width: 100%; margin: 5px;">
            </div>
            <section class="" style="width: 100%;height: 240px;">

                <div class=""  style="height: 50px;">
                    <span class="badge badge-dark">基本信息</span>
                    <el-tag style="margin-left: 5px;"
                            effect="dark">
                        {{ education[0].time }}
                    </el-tag>

                    <el-tag style="margin-left: 5px;"
                            effect="dark">
                        {{ education[0].school }}
                    </el-tag>

                    <el-tag style="margin-left: 5px;"
                            effect="dark">
                        {{ education[0].professional }}
                    </el-tag>

                    <el-tag style="margin-left: 5px;"
                            effect="dark">
                        {{ education[0].degree }}
                    </el-tag>

                    <el-tag style="margin-left: 5px;"
                            effect="dark">
                        {{ education[0].PoliticalStatus }}
                    </el-tag>
                </div>

                <div class="" style="height: 50px; ">
                    <span class="badge badge-dark">专业课程</span>

                    <el-tag style="margin-left: 5px;" v-for="item in education[0].course"
                                effect="dark">
                            {{ item.label }}
                    </el-tag>
                </div>

                <div class="" style="height: 50px; ">
                    <span class="badge badge-dark">专业奖项</span>
                    <el-tag style="margin-left: 5px;" v-for="item in education[0].professionalscore"
                            effect="dark">
                        {{ item }}
                    </el-tag>
                </div>

                 <div class="" style="height: 50px; ">
                    <span class="badge badge-dark">校内奖项</span>
                    <el-tag style="margin-left: 5px;" v-for="item in education[0].schoolscore"
                            effect="dark">
                        {{ item }}
                    </el-tag>
                </div>

                <div class="" style="height: 50px; ">
                    <span class="badge badge-dark">在校经历</span>
                    <el-tag style="margin-left: 5px;" v-for="item in education[0].event"
                            effect="dark">
                        {{ item }}
                    </el-tag>
                </div>

            </section>

            <!--实习经历-->
            <div class="work_experience" style="margin-top: 30px;">
                <h2><span class="badge badge-info">{{work_experience}}</span></h2>
                <hr style="border-top: 1px solid #161515; width: 100%; margin: 5px;">
            </div>
             <section class="" style="width: 100%;height: 520px;" v-for="item in work_info">
                 <div>
                     <span class="badge badge-dark">基本信息</span>
                      <el-tag style="margin-left: 5px;"
                            effect="dark">
                        {{item.times }}
                    </el-tag>
                   <el-tag style="margin-left: 5px;"
                            effect="dark">
                        {{ item.company }}
                    </el-tag>
                   <el-tag style="margin-left: 5px;"
                            effect="dark">
                        {{ item.job_position }}
                    </el-tag>
                 </div>

                 <div>
                     <span class="badge badge-dark">项目介绍</span>
                     <div class="alert alert-light" role="alert" style="color: #33aef0">
                         {{ item.describe}}
                    </div>
<!--                     <p >{{ item.describe}}</p>-->
                 </div>


                  <div>
                     <span class="badge badge-dark">关键技术</span>
                      <el-tag style="margin-left: 5px;" v-for="item1 in item.technics"
                            effect="dark">
                        {{ item1 }}
                    </el-tag>
                 </div>
                 <div>
                     <span class="badge badge-dark">主要职责</span>
                     <ul class="list-group list-group-flush" style="padding-top: 10px;">
                      <li class="list-group-item" v-for="item2 in item.values">
                          {{ item2  }}
                      </li>
                    </ul>
                 </div>

             </section>

            <!--项目经历-->
            <div class="project_experience" style="margin-top: 30px;">
                <h2><span class="badge badge-info">{{project_experience}}</span></h2>

                <hr style="border-top: 1px solid #161515; width: 100%; margin: 5px;">
            </div>
             <section class="" style="width: 100%;height:480px;" v-for="item in person_info">
                  <div style="margin-bottom: 5px;">
                     <span class="badge badge-danger">项目名</span>
                      <el-tag style="margin-left: 5px;"
                            effect="dark">
                        {{ item.proname }}
                        </el-tag>
                      <i class="el-icon-s-home" style="height: 100%;"><a v-bind:href=item.info>Github</a></i>
                 </div>
                <div>
                     <span class="badge badge-dark">基本信息</span>
                      <el-tag style="margin-left: 5px;"
                            effect="dark">
                        {{ item.times }}
                    </el-tag>
                   <el-tag style="margin-left: 5px;"
                            effect="dark">
                        {{ item.proname }}
                    </el-tag>
                   <el-tag style="margin-left: 5px;"
                            effect="dark">
                        {{ item.note }}
                    </el-tag>
                 </div>

                 <div>
                     <span class="badge badge-dark" >项目介绍</span>
<!--                     <p >{{ item.describe}}</p>-->
                      <div class="alert alert-light" role="alert" style="color: #33aef0;padding-top:5px;padding-bottom:5px;">
                         {{ item.describe}}
                    </div>
                 </div>


                  <div>
                     <span class="badge badge-dark">关键技术</span>
                      <el-tag style="margin-left: 5px;" v-for="item1 in item.technics"
                            effect="dark">
                        {{ item1 }}
                    </el-tag>
                 </div>


                 <div>
                     <span class="badge badge-dark">主要职责</span>
                     <ul class="list-group list-group-flush" style="padding-top: 10px;">
                      <li class="list-group-item" v-for="item2 in item.values">
                          {{ item2  }}
                      </li>
                    </ul>
                 </div>
             </section>
             <section class="" style="width: 100%;height:185px; margin-top: 30px;" v-for="item in person_sminfo">
                  <div style="margin-bottom: 5px;">
                     <span class="badge badge-danger">项目名</span>
                      <el-tag style="margin-left: 5px;"
                            effect="dark">
                        {{ item.proname }}
                      </el-tag>
                      <i class="el-icon-s-home" style="height: 100%;"><a v-bind:href=item.info>Github</a></i>
                 </div>
                <div>
                     <span class="badge badge-dark">基本信息</span>
                      <el-tag style="margin-left: 5px;"
                            effect="dark">
                        {{ item.times }}
                    </el-tag>
                   <el-tag style="margin-left: 5px;"
                            effect="dark">
                        {{ item.proname }}
                    </el-tag>
                   <el-tag style="margin-left: 5px;"
                            effect="dark">
                        {{ item.note }}
                    </el-tag>
                 </div>

                 <div>
                     <span class="badge badge-dark">项目介绍</span>
<!--                     <p >{{ item.describe}}</p>-->
                      <div class="alert alert-light" role="alert" style="color: #33aef0;padding-top:0;padding-bottom:0;">
                         {{ item.describe}}
                    </div>
                 </div>
                  <div>
                     <span class="badge badge-dark">关键技术</span>
                      <el-tag style="margin-left: 5px;" v-for="item1 in item.technics"
                            effect="dark">
                        {{ item1 }}
                    </el-tag>
                 </div>

             </section>

            <!--专业技能-->
            <div class="skills" style="margin-top: 30px;">
                 <h2><span class="badge badge-info">{{skills}}</span></h2>
                <hr style="border-top: 1px solid #161515; width: 100%; margin: 5px;">
            </div>
             <section class="" style="width: 100%;height: 700px;">
                 <div>
                      <span class="badge badge-dark">技能描述</span>
                      <ul class="list-group list-group-flush" style="padding-top: 10px;">
                          <li class="list-group-item" v-for="item in skills_info">
                             {{ item.id  }}.{{ item.skillname  }}
                          </li>
                      </ul>
                 </div>

                 <div>
                     <span class="badge badge-dark">技能可视化</span>
                     <el-progress :text-inside="true"  v-for="item in skills_info" :stroke-width="20" :percentage="item.score" v-bind:status=selcolor(item.score) style="padding-top: 5px;"></el-progress>
                 </div>

             </section>
        </div>

    </div>


</template>

<script>
    import 'bootstrap/dist/css/bootstrap.min.css'
    import 'bootstrap/dist/js/bootstrap.min.js'
    import userImg from '../assets/images/user.jpg'

    export default {
        components: {  /* 前面的组件名称不能和HTML标签一样*/

        },
        methods:{
            selcolor(score){
                if(score < 60)
                    return "exception"
                else if (80 > score && score >= 60)
                    return "warning"
                else if (90 > score &&  score>= 80)
                    return null
                else if (100 >= score && score>= 90)
                    return "success"
            },
        },
        data() {
            return {
                img: userImg,
                name: '文理',
                age: 21,
                sex: '男',
                email: '943955239@qq.com',
                phone: '15629870321',
                github: 'https://github.com/Angell1',
                blog: 'https://www.cnblogs.com/-wenli/',
                job: '后端开发',
                personinfo:'go / python程序员，涉及到：Mysql，Redis，Rabbitmq，分布式，中间件技术，缓存，docker，k8s。',
                personextra:'保持学习，保持理性，保持健康',

                education_ba: '教育背景',
                education: [
                    {
                        time: '2017-2021',
                        school: '湖北工程学院',
                        professional: '电子信息工程',
                        degree: '本科',
                        PoliticalStatus: '共青团员',
                        course: [
                            {type: '', label: 'C语言'},
                            {type: '', label: '嵌入式'},
                            {type: '', label: '数据结构'},
                            {type: '', label: '计算机网络'},
                            {type: '', label: '数模电'}
                        ],
                        professionalscore: ['全国大学生电子设计大赛省二等奖', '恩智浦智能车省一等奖'],
                        schoolscore:['计算机二级','优秀共青团员','活动积极分子','摄影大赛二等奖'],
                        event:['参与家电维修志愿服务','参与院级媒体工作','参与实验室项目'],
                    }
                ],

                work_experience: '实习经历',
                work_info: [
                    {
                        id: '1',
                        times:'2020.07.03-2020.10.21',
                        company: '广东博智林机器人',
                        job_position: 'Python后端开发',
                        technics:['Python','Django','Rabbitmq','Celery','Redis','Mysql'],
                        describe: '  通用化语音质检平台，支持多角色配置，支持多质检模型配置，质检规则的多样化配置，大规模语音的并行质检，质检任务质检状态实时更新，质检数据的数据统计，并支持质检结果的人工复查。',
                        values: [
                            '1. 对接讯飞接口进行语音质检；',
                            '2. 语音查询、排序、筛选，质检状态更新等接口编写；',
                            '3. 使用Celery对语音上传、语音处理进行异步处理与定时处理并进行后续优化；',
                            '4. 使用Rabbitmq传输组件之间的数据；',
                            '5. 使用Redis缓存查询相关接口数据，并作为组件间临时数据存储的中间件；',
                            '6. 测试服务器部署及维护，接口文档的编写与整理；',
                            '7. 使用Pycharm、PostMan、Git、Linux、Navicat进行日常开发工作。',
                            ],
                        info:'项目外：负责部门K8S平台搭建与维护。'
                    },

                ],

                project_experience: '项目经历',
                person_info: [
                    {
                        id: '1',
                        proname:'分布式k-v系统',
                        note:'个人项目',
                        times:'2019.07 - 2019.11',
                        technics:['Go','Rabbitmq','HTTP服务器','一致性哈希算法','内存池'],
                        describe: '分布式k-v系统',
                        values: [
                            '1. 采用分布式的项目开发模式，整个项目分为：API网关、Rabbitmq服务器，数据节点服务；',
                            '2. 基于Rabbitmq进行心跳服务通信，实现数据节点与API网关的通信；',
                            '3. 数据节点采用shard map+读写锁实现内存池，数据过期策略为LRU与超时过期机制；',
                            '4. 分布式路由使用一致性哈希算法，可以任意添加、删除节点；',
                            '5. 使用go-metrics对API网关进行应用级监控、统计；',
                            ],
                        info:''
                    },
                    {
                        id: '2',
                        proname:'个人求职中心',
                        times:'2019.07 - 2019.11',
                        note:'个人项目',
                        technics:['Python','Django','Mysql','Celery','MongoDB','Vue','BootStarp','ElementUI'],
                        describe: '为个人提供完整服务的招聘信息整合网站，为解决无法找到最新、更为匹配的岗位信息。',
                        values: [
                            '1. Django实现用户管理与权限管理，并实现网站前台后台逻辑；',
                            '2. Celery实现定时爬取招聘网站数据，做相关预处理，写入数据库，并清除数据库过期时效数据；',
                            '3. Mysql存储核心数据，如用户、用户统计数据、岗位统计数据；',
                            '4. MongoDB存储岗位相关数据；',
                            '5. 支持在线微简历，根据微简历为用户推荐更为匹配的岗位；',
                            '6. 支持一键邮箱投递匹配岗位；',
                            ],
                        info:''
                    },
                ],
                person_sminfo: [
                    {
                        id: '1',
                        proname:'心跳服务器',
                        note:'个人项目',
                        times:'2020.07 - 2020.08',
                        technics:['Python','线程池','多路复用IO','任务队列'],
                        describe: 'Python编写的TCP心跳服务器，架构为多路复用IO+任务队列+线程池。',
                        info:'https://github.com/Angell1/Heart_Server'
                    },
                    {
                        id: '2',
                        proname:'Tcp服务器',
                        note:'个人项目',
                        times:'2020.01 - 2020.02',
                        technics:['Go','工作池','内存池','任务队列'],
                        describe: 'Go编写的Tcp服务器，架构为任务队列 + 工作池 + 内存池，读写进行分离，采样模块化编程，分为Server模块、链接属性配置模块、消息封装模块、基础路由模块、全局配置模块，多路由模块，链接管理模块。',
                        info:''
                    },
                    {
                        id: '3',
                        proname:'函数调用追踪与分析',
                        note:'个人项目',
                        times:'2020.07 - 2020.08',
                        technics:['Python','Redis'],
                        describe: '在日常工作中，代码中函数间的的调用往往是多层次的，造成在分析函数调用耗时难以下手,而引入更为复杂的分布式调用追踪不是明智的选择，Python项目的函数调用追踪，利用上下文管理器，可对函数连续、独立、' +
                            '并级调用进行追踪分析，支持日志扩展。',
                        info:''
                    },
                    {
                        id: '4',
                        proname:'Rabbitmq连接池',
                        note:'个人项目',
                        times:'2020.08 - 2020.09',
                        technics:['Python','Rabbitmq'],
                        describe: '支持Python的Rabbitmq连接池,多连接模板支持，多主机配置。',
                        info:'https://github.com/Angell1/Pyrabbitmq'
                    },
                ],

                skills: '技能',
                skills_info: [
                    {
                        id: '1',
                        skillname: '熟悉链表、栈、队列、排序、查找等数据结构与算法，熟练编写C代码；',
                        score:80,
                    },
                    {
                        id: '2',
                        skillname: '熟悉HTTP、TCP协议，熟练使用Linux部署服务及开发，使用git进行代码迭代与管理，了解Nginx+lua组合；',
                        score:85,
                    },

                    {
                        id: '3',
                        skillname: '熟悉Python开发及其基础模块、熟悉Python Django框架，熟悉drf开发；',
                        score:85,
                    },
                    {
                        id: '4',
                        skillname: '熟悉Go，Channel、Goroutine，熟悉Go CSP编程,使用Gin进行Web开发；',
                        score:75,
                    },
                    {
                        id: '5',
                        skillname: '熟悉Redis常用数据结构及其应用（缓存、消息队列、分布式锁、限流等），了解MongoDB及SSDB； ',
                        score:85,
                    },
                    {
                        id: '6',
                        skillname: '熟悉Rabbitmq消息队列及相关生产实践； ',
                        score:90,
                    },
                    {
                        id: '7',
                        skillname: '熟悉Mysql的索引与事务机制，及编写sql语句； ',
                        score:85,
                    },
                    {
                        id: '8',
                        skillname: '熟悉Docker，了解k8s,及相关监控、日志开源生态； ',
                        score:85,
                    },

                ],

                other: '其他',
                other_list: [
                    {
                        id: '1',
                        hobby: '骑行',

                    },
                    {
                        id: '2',
                        name: '美食',
                    }
                ]
            }
        }
    }
</script>


<style lang="scss" scoped>
    #resume {
        background-color: #fff;
        padding-top: 50px;
        opacity:0.7;
    }
</style>
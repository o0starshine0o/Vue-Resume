<template>
<div class='container'>
    <div class='header-container'>
        <div class='portrait-container'>
            <img src='./life-picture-square.jpg'></img>
            <a class='title'>{{ baseInfo.name }}</a>
        </div>
        <div class='connect-container sub-title'>
            <a><i class="iconfont icon-email"></i> {{ contentInfo.email }}</a>
            <a><i class="iconfont icon-wechat"></i> {{ contentInfo.wechat }}</a>
            <a><i class="iconfont icon-qq"></i> {{ contentInfo.qq }}</a>
        </div>
    </div>
    <div class='info-container'>
        <div class='title-container'>
            <span class='pre-icon'></span>
            <a class='title'>基本信息</a>
        </div>
        <div class='content-container content'>
            <div>
                <a style='flex-grow:1'>性别：{{ baseInfo.sex }}</a>
                <a style='flex-grow:1'>生日：{{ baseInfo.birthday }}</a>
            </div>
            <div>
                <a>毕业院校：{{ baseInfo.collage }}</a>
            </div>
            <div>
                <a >github：</a>
                <a :href='baseInfo.github'>本项目链接(还有很多私有项目)</a>
            </div>
        </div>
    </div>
    <div class='info-container'>
        <div class='title-container'>
            <span class='pre-icon'></span>
            <a class='title'>项目经验</a>
        </div>
        <template v-for='experence in experences'>
            <div class='content-container content'>
                <div class='company-container'>
                    <img class='logo' :src='experence.company.logo'></img>
                    <div>
                        <a class='sub-title'>{{ experence.company.name }}</a>
                        <a class='sub-title'>（{{ experence.company.time }}）</a>
                    </div>
                </div>
                <template v-for='project in experence.projects'>
                    <div class='project-container'>
                        <div class='slide'>
                            <div class='dot'></div>
                            <div class='vertical-line'></div>
                        </div>
                        <div class='production-container'>
                            <div class='production-name'>
                                <a>{{ project.name }}</a>
                            </div>
                            <div class='production-desc'>
                                <a>{{ project.desc }}</a>
                            </div>
                            <div class='production-image'>
                                <template v-for='image in project.images'>
                                    <img :src='image'></img>
                                </template>
                            </div>
                        </div>
                    </div>
                </template>
            </div>
        </template>
    </div>
    <div class='info-container'>
        <div class='title-container'>
            <span class='pre-icon'></span>
            <a class='title'>结尾废话</a>
        </div>
        <div class='content-container content'>
            <div>
                <a>{{ baseInfo.nonsense }}{{ baseInfo.hope }}</a>
            </div>
        </div>
    </div>
</div>
</template>

<style>
.icon {
    width: 1em; height: 1em;
    vertical-align: -0.15em;
    fill: currentColor;
    overflow: hidden;
}
</style>

<style>
@import "iconfont.css";
div{
    display: flex;
    flex-grow: 1;
    overflow: hidden;
}

.slide{
    flex-direction: column;
    align-items: center;
    width: 30px;
    flex-grow: 0;
    margin: 0 20px;
}

.dot{
    width: 30px;
    height: 30px;
    border-radius: 2000px;
    background: #30b6b6;
    flex-grow: 0;
    margin-top: 8px;
}

.vertical-line{
    width: 5px;
    background: #30b6b6;
}

.title{
    font-size: 50px;
    color: #30b6b6;
}

.sub-title{
    font-size: 38px;
    color: #30b6b6;
}

.content {
    font-size: 20px;
    color: #353535;
}

.logo {
    width: 60px;
    height: 60px;
    margin: 10px;
    border-radius: 2000px;
}

.pre-icon{
    width: 10px;
    height: 50px;
    background: #30b6b6;
    margin: 10px;
}

.container{
    flex-direction: column;
}

.header-container {
    height: 400px;
    background: #30b6b6;
    flex-direction: column;
}

.header-container a{
    color: #ffffff;
}

.portrait-container{
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.portrait-container img{
    width: 160px;
    height: 160px;
    border-radius: 2000px;
}

.connect-container {
    justify-content: space-around;
    align-items: center;
}

.connect-container .iconfont {
    font-size: 40px;
}

.info-container {
    margin: 10px;
    flex-direction: column;
}

.title-container {
    align-items: center;
}

.content-container{
    flex-direction: column;
    margin-left: 40px;
}

.company-container{
    justify-content: center;
    align-items: center;
}

.production-container{
    flex-direction: column;
}

.production-name{
    flex-grow: 0;
    font-size: 30px;
    color: #353535;
}

.production-desc{
    flex-grow: 0;
    font-size: 26px;
    color: #666666;
}

.production-image{
    max-width: 96%;
}

.production-image img{
    max-height: 300px;
    justify-content: center;
}
</style>

<script>
export default {
    data(){
        return {
            baseInfo: {
                name: '胡永胜',
                sex: '男',
                birthday: '1992-03-20',
                collage: '华中科技大学-软件学院（14届）',
                github: 'https://github.com/o0starshine0o/',
                nonsense: '周末上午听到王杰老师的节目，下午就开始学习Vue了，顺便就用Vue做了个简历，希望能得到重视。因为只是学习没有搭建完整的开发环境，就用纯文本编辑器做了这份简历。我14年毕业，16年和朋友合伙创业，18年散伙了(T_T)。创业期间几乎包揽了所有的开发工作，服务器用的Python-Django，客户端包括了：Android、iOS、Web、H5、公众号、小程序···但凡普通用户能接触到的客户端都做了，当然也包括最近还完成的快应用。',
                hope: '如果有机会能与王杰老师一起工作，我希望能通过IT男的一些努力把科学声音做好，也希望能把传播科学声音作为自己的事业。',
            },
            contentInfo:{
                email: 'tohys@qq.com',
                wechat: 'husthys',
                qq: '765870829'
            },
            experences:[
                {
                    company: {
                        logo: require('./qicode.png'),
                        name: '北京启码时代科技有限公司',
                        time: '2016.02-至今'
                    },
                    projects:[
                        {
                            name: '签名设计',
                            desc: '负责项目的：服务器、iOS、Web、Android、小程序、H5、快应用···其中小程序从学习到完成耗时5天（不包含支付，当时支付遇到了大坑），快应用从学习到上线耗时10天，学习了flex布局，最开始尝试通过小程序转换，但是发现转换后的代码根本没法维护就重新开始制作了。',
                            images:[
                                require('./qicode/01.jpg'),
                                require('./qicode/02.jpg'),
                                require('./qicode/03.jpg'),
                                require('./qicode/04.jpg'),
                                require('./qicode/05.jpg'),
                            ]
                        },
                        {
                            name: '起名设计',
                            desc: '负责项目的：服务器、iOS、Web、Android、公众号、H5···值得一提的是在线起名是通过TensorFlow来完成的：先通过Python爬虫抓取了各类起名网站上百万条有效名字，通过LSTM训练这些数据，最终能通过了有限的图灵测试。',
                            images:[
                                require('./name/0.jpg'),
                                require('./name/1.jpg'),
                                require('./name/2.jpg'),
                                require('./name/3.jpg'),
                                require('./name/4.jpg'),
                            ]
                        }
                    ]
                },
                {
                    company: {
                        logo: require('./art.png'),
                        name: '北京千渡网讯科技有限公司',
                        time: '2015.06-2016.02'
                    },
                    projects:[
                        {
                            name: '手机鉴宝',
                            desc: '最开始过去是做Android的（2人合作），做完之后用了一个月的时间学习并做完了iOS版的（1周后上线成功）。当时正好storyboard，swift都已经发布了，就采用最新的方案进行开发了。',
                            images:[
                                require('./art/0.jpeg'),
                                require('./art/1.jpeg'),
                                require('./art/2.jpeg'),
                                require('./art/3.jpeg'),
                                require('./art/4.jpeg'),
                            ]
                        }
                    ]
                },
                {
                    company: {
                        logo: require('./kika.jpeg'),
                        name: '北京新美互通科技有限公司',
                        time: '2014.07-2015.06'
                    },
                    projects:[
                        {
                            name: '直装字体',
                            desc: '毕业后第一家公司。比较有意思的是《直装字体》最开始是老大写的代码，我接手后觉得代码简直“惨不忍睹”，和团队成员沟通后就全部删除并重新写了。(产品只发布在Google Play上)',
                            images:[
                                require('./font/0.webp'),
                                require('./font/1.webp'),
                                require('./font/2.webp'),
                                require('./font/3.webp'),
                                require('./font/4.webp'),
                            ]
                        }
                    ]
                },
            ]
        }
    }
}
</script>

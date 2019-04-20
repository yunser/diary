<template>
    <my-page title="日记" :page="page">
        暂不对外开放
    </my-page>
</template>

<script>
    /* eslint-disable */
    const moment = window.moment
    import {timeFilter, commonTimeFilter} from '@/util/filter'
    import {cms} from '@/config'

    export default {
        data () {
            return {
                pagination: {
                    page: 1,
                    totalPage: 1
                },
                articles: [],
                page: {
                    menu: [
                        {
                            type: 'icon',
                            icon: 'apps',
                            href: 'https://app.yunser.com?utm_source=app',
                            target: '_blank',
                            title: '应用'
                        }
                    ]
                }
            }
        },
        mounted() {
            window.addEventListener('keydown', this.keyDown = e => {
                console.log(e.keyCode)
                if (e.keyCode === 69) {
                    this.$router.push('/diaries')
                }
            })
        },
        destroyed() {
            window.removeEventListener('keydown', this.keyDown)
        },
        destroyed() {
        },
        methods: {
        },
    }
</script>

<style lang="scss" scoped>
.page-home {
    background-color: #eee;
}
.slogan {
    font-size: 32px;
    margin-bottom: 16px;
}
.article-box {
    background-color: #fff;
}
.news-list {
    .item {
        display: flex;
        align-content: space-between;
        padding: 16px 0;
        // margin-bottom: 16px;
        border-bottom: 1px solid rgba(0, 0, 0, .12);
    }
    .title {
        display: flex;
        align-items: center;
        margin-bottom: 16px;
        font-size: 16px;
        font-weight: bold;
        color: #333;
    }
    .top {
        margin-right: 8px;
    }
    .meta {
        display: flex;
        align-items: center;
        margin-bottom: 8px;
    }
    .avatar {
        display: block;
        width: 16px;
        height: 16px;
        margin-right: 4px;
        border-radius: 50%;
    }
    .user-name {
        color: #666;
        margin-right: 16px;
    }
    .time {
        color: #999;
    }
    .tag {
        margin-right: 8px;
    }
}
.more {
    margin-top: 16px;
}
.icp {
    text-align: center;
    margin-top: 16px;
    margin-bottom: 16px;
}
</style>

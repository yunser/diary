<template>
    <my-page :title="title" :page="page" backable>
        <h1 class="article-title">{{ article.title }}</h1>
        <ui-article v-html="article.content">
        </ui-article>
    </my-page>
</template>

<script>
    export default {
        data () {
            return {
                title: '日记详情',
                article: {},
                page: {
                    menu: [
                        // {
                        //     type: 'icon',
                        //     icon: 'apps',
                        //     href: 'https://app.yunser.com/',
                        //     target: '_blank',
                        //     title: '应用'
                        // }
                        // {
                        //     type: 'icon',
                        //     icon: 'help',
                        //     to: '/help'
                        // }
                    ]
                }
            }
        },
        mounted() {
            let id = this.$route.params.id
            this.$http.get(`/articles/${id}?convert=true`).then(
                response => {
                    let data = response.data
                    this.article = data
                    this.title = this.article.title
                },
                response => {
                    console.log(response)
                })
        }
    }
</script>

<style lang="scss" scoped>
.article-title {
    font-size: 24px;
    font-weight: bold;
    margin-bottom: 24px;
}
</style>

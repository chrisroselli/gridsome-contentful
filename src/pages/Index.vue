<template>
  <Layout>
  
    <!-- Learn how to use images here: https://gridsome.org/docs/images -->
    <g-image alt="Example image" src="~/favicon.png" width="135" />   

  <h1>{{$page.contentfulPage.title}}</h1>
  <p v-html="richtextToHTML($page.contentfulPage.mainContent)"></p>
  </Layout>
</template>

<page-query>
query Page {
	contentfulPage(id:"695ls1eS7WSVhC1ZhV5gaz") {
    id
    title
    mainContent
  }
}
</page-query>

<script>
import { documentToHtmlString } from '@contentful/rich-text-html-renderer'
export default {
  metaInfo: {
    title: 'Gridsome Contentful'
  },
    methods: {
    richtextToHTML (content) {
      return documentToHtmlString(content)
    }
  }
}
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>

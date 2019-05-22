<template>
  <Layout>
    
<h1>{{$page.contentfulPage.title}}</h1>
<p v-html="richtextToHTML($page.contentfulPage.mainContent)"></p>
  </Layout>
</template>

<page-query>
query Page {
	contentfulPage(id:"7KeAXmdIkIQM3RAvFNjJ0t") {
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
    title: 'About us'
  },
    methods: {
    richtextToHTML (content) {
      return documentToHtmlString(content)
    }
  }
}
</script>

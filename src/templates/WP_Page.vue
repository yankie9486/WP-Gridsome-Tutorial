<template>
<layout>
    <section class="section">
        <div class="container">
            <h1 v-html="$page.page.title" />
            <div v-if="$page.page.featuredImage" class="featured-image">
                <img :src="$page.page.featuredImage.sourceUrl" />
            </div>
            <div v-html="$page.page.content" />
        </div>
    </section>

</layout>
</template>

<page-query>
query Page ($slug: String) {
	page: pageBy(uri: $slug) {
        title
        content
        featuredImage{
            sourceUrl
            altText
        }
	}
}
</page-query>

<script>
    export default {
        metaInfo: {
            title: ''
        }
    }
</script>

<style>

.container {
    max-width: 1200px;
    margin-right: auto;
    margin-left: auto;
}

</style>
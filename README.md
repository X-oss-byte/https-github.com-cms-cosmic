# A statically generated blog example using Next.js and Cosmic

This example showcases Next.js's [Static Generation](https://nextjs.org/docs/basic-features/pages) feature using [Cosmic](https://cosmicjs.com/) as the data source.

## Demo

[https://cosmic-next-blog.vercel.app/](https://cosmic-next-blog.vercel.app/)

## Deploy your own

Once you have access to [the environment variables you'll need](#step-3-set-up-environment-variables), deploy the example using [Vercel](https://vercel.com?utm_source=github&utm_medium=readme&utm_campaign=next-example):

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/vercel/next.js/tree/canary/examples/cms-cosmic&project-name=cms-cosmic&repository-name=cms-cosmic&env=COSMIC_BUCKET_SLUG,COSMIC_READ_KEY,COSMIC_PREVIEW_SECRET&envDescription=Required%20to%20connect%20the%20app%20with%20Cosmic&envLink=https://vercel.link/cms-cosmic-env)

### Related examples

- [AgilityCMS](/examples/cms-agilitycms)
- [Builder.io](/examples/cms-builder-io)
- [ButterCMS](/examples/cms-buttercms)
- [Contentful](/examples/cms-contentful)
- [Cosmic](/examples/cms-cosmic)
- [DatoCMS](/examples/cms-datocms)
- [DotCMS](/examples/cms-dotcms)
- [Drupal](/examples/cms-drupal)
- [Enterspeed](/examples/cms-enterspeed)
- [Ghost](/examples/cms-ghost)
- [GraphCMS](/examples/cms-graphcms)
- [Kontent](/examples/cms-kontent-ai)
- [Prepr](/examples/cms-prepr)
- [Prismic](/examples/cms-prismic)
- [Sanity](/examples/cms-sanity)
- [Sitefinity](/examples/cms-sitefinity)
- [Storyblok](/examples/cms-storyblok)
- [TakeShape](/examples/cms-takeshape)
- [Umbraco heartcore](/examples/cms-umbraco-heartcore)
- [Webiny](/examples/cms-webiny)
- [Blog Starter](/examples/blog-starter)
- [WordPress](/examples/cms-wordpress)

## How to use

Execute [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app) with [npm](https://docs.npmjs.com/cli/init), [Yarn](https://yarnpkg.com/lang/en/docs/cli/create/), or [pnpm](https://pnpm.io) to bootstrap the example:

```bash
npx create-next-app --example cms-cosmic cms-cosmic-app
```

```bash
yarn create next-app --example cms-cosmic cms-cosmic-app
```

```bash
pnpm create next-app --example cms-cosmic cms-cosmic-app
```

## Configuration

### Step 1. Create an account and a project on Cosmic

First, [create an account on Cosmic](https://cosmicjs.com).

### Step 2. Install the Next.js Static Blog app

After creating an account, install the [Next.js Static Blog](https://www.cosmicjs.com/apps/nextjs-static-blog) app from the Cosmic App Marketplace.

### Step 3. Set up environment variables

Go to the **Settings** menu at the sidebar and click **Basic Settings**.

Next, copy the `.env.local.example` file in this directory to `.env.local` (which will be ignored by Git):

```bash
cp .env.local.example .env.local
```

Then set each variable on `.env.local`:

- `COSMIC_BUCKET_SLUG` should be the **Bucket slug** key under **API Access**.
- `COSMIC_READ_KEY` should be the **Read Key** under **API Access**.
- `COSMIC_PREVIEW_SECRET` can be any random string (but avoid spaces) - this is used for [Preview Mode](https://nextjs.org/docs/advanced-features/preview-mode).

Your `.env.local` file should look like this:

```bash
COSMIC_BUCKET_SLUG=...
COSMIC_READ_KEY=...
COSMIC_PREVIEW_SECRET=...
```

### Step 4. Run Next.js in development mode

```bash
npm install
npm run dev

# or

yarn install
yarn dev
```

Your blog should be up and running on [http://localhost:3000](http://localhost:3000)! If it doesn't work, post on [GitHub discussions](https://github.com/vercel/next.js/discussions).

### Step 5. Try preview mode

To add the ability to preview content from your Cosmic dashboard go to **Posts > Edit Settings** and scroll down to the "Preview Link" section. (Screenshot below)

![Image](https://cdn.cosmicjs.com/14e6c0f0-a07b-11ea-829b-5b458b05d525-preview-link.png)

Add your live URL or localhost development URL which includes your chosen preview secret and `[object_slug]` shortcode. It should look like the following:

```
http://localhost:3000/api/preview?secret=<secret>&slug=[object_slug]
```

- `<secret>` is the string you entered for `COSMIC_PREVIEW_SECRET`.
- `[object_slug]` shortcode will automatically be converted to the post's `slug` attribute.

On Cosmic, go to one of the posts you've created and:

- **Update the title**. For example, you can add `[Draft]` in front of the title.
- Click **Save Draft**, but **DO NOT** click **Publish**. By doing this, the post will be in the draft state.

Now, if you go to the post page directly on localhost, you won't see the updated title. However, if you use the **Preview Mode**, you'll be able to see the change ([Documentation](https://nextjs.org/docs/advanced-features/preview-mode)).

Next, click the Preview Link button on the Post to see the updated title. (Screenshot below)

<img src="https://cdn.cosmicjs.com/80f42680-a07a-11ea-829b-5b458b05d525-preview-button.png" width="300" />

To exit preview mode, you can click on **Click here to exit preview mode** at the top.

### Step 6. Deploy on Vercel

You can deploy this app to the cloud with [Vercel](https://vercel.com?utm_source=github&utm_medium=readme&utm_campaign=next-example) ([Documentation](https://nextjs.org/docs/deployment)).

#### Deploy Your Local Project

To deploy your local project to Vercel, push it to GitHub/GitLab/Bitbucket and [import to Vercel](https://vercel.com/new?utm_source=github&utm_medium=readme&utm_campaign=next-example).

**Important**: When you import your project on Vercel, make sure to click on **Environment Variables** and set them to match your `.env.local` file.

#### Deploy from Our Template

Alternatively, you can deploy using our template by clicking on the Deploy button below.

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/vercel/next.js/tree/canary/examples/cms-cosmic&project-name=cms-cosmic&repository-name=cms-cosmic&env=COSMIC_BUCKET_SLUG,COSMIC_READ_KEY,COSMIC_PREVIEW_SECRET&envDescription=Required%20to%20connect%20the%20app%20with%20Cosmic&envLink=https://vercel.link/cms-cosmic-env)


<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <link href="https://fonts.googleapis.com/css?family=Roboto" rel="stylesheet">
  <meta name="generator" content="Google Web Designer 15.2.1.0306">
  <meta data-template-name="gwd-AppIn_Cstm_Shk_To_Rev_320x480">
  <meta name="template" content="Interstitial 2.2.4">
  <meta name="environment" content="gwd-googleads">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="gwdpage_style.css" rel="stylesheet" data-version="13" data-exports-type="gwd-page">
  <link href="gwdpagedeck_style.css" rel="stylesheet" data-version="14" data-exports-type="gwd-pagedeck">
  <link href="gwdgesture_style.css" rel="stylesheet" data-version="7" data-exports-type="gwd-gesture">
  <link href="gwdimage_style.css" rel="stylesheet" data-version="17" data-exports-type="gwd-image">
  <link href="gwdgallerynavigation_style.css" rel="stylesheet" data-version="8" data-exports-type="gwd-gallerynavigation">
  <link href="gwdcarouselgallery_style.css" rel="stylesheet" data-version="25" data-exports-type="gwd-carouselgallery">
  <link href="gwdattached_style.css" rel="stylesheet" data-version="2" data-exports-type="gwd-attached">
  <link href="gwdgooglead_style.css" rel="stylesheet" data-version="9" data-exports-type="gwd-google-ad">
  <link href="gwdstarratings_style.css" rel="stylesheet" data-version="3" data-exports-type="gwd-starratings">
  <link href="gwdtaparea_style.css" rel="stylesheet" data-version="7" data-exports-type="gwd-taparea">
  <style id="gwd-center-page-style">
    #page1 {
      left: 50%;
      top: 50%;
      margin-left: -160px;
      margin-top: -240px;
    }
    #page1_1 {
      left: 50%;
      top: 50%;
      margin-left: -240px;
      margin-top: -160px;
    }
    #page1_2 {
      left: 50%;
      top: 50%;
      margin-left: -240px;
      margin-top: -160px;
    }
    #page1_3 {
      left: 50%;
      top: 50%;
      margin-left: -160px;
      margin-top: -240px;
    }
  </style>
  <style id="gwd-lightbox-style">
    .gwd-lightbox {
      overflow: hidden;
    }
  </style>
  <style>
    html, body {
      width: 100%;
      height: 100%;
      margin: 0px;
    }
    .gwd-page-container {
      position: relative;
      width: 100%;
      height: 100%;
    }
    .gwd-page-content {
      transform: perspective(1400px) matrix3d(1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1);
      transform-style: preserve-3d;
      position: absolute;
      background-color: transparent;
    }
    .gwd-page-content * {
      transform-style: preserve-3d;
    }
    .gwd-page-wrapper {
      position: absolute;
      transform: translateZ(0px);
      background-color: rgb(255, 255, 255);
    }
    .gwd-page-size {
      width: 300px;
      height: 250px;
    }
    .gwd-div-13rh {
      width: 320px;
      height: 480px;
    }
    .gwd-div-1118 {
      width: 320px;
      height: 480px;
    }
    .gwd-div-yjjv {
      position: absolute;
      left: 0px;
      top: 0px;
      width: 320px;
      height: 480px;
      opacity: 0.5;
      background-image: none;
      background-color: rgb(0, 0, 0);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-13vi {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 0px;
      transform-style: preserve-3d;
      top: 0px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-ek5n {
      position: absolute;
      left: 64px;
      width: 64px;
      height: 48px;
      transform-style: preserve-3d;
      top: 0px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-1qnx {
      position: absolute;
      height: 48px;
      left: 128px;
      width: 64px;
      transform-style: preserve-3d;
      top: 0px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-wvbf {
      position: absolute;
      height: 48px;
      left: 192px;
      width: 64px;
      transform-style: preserve-3d;
      top: 0px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-ttao {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 256px;
      transform-style: preserve-3d;
      top: 0px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-86di {
      position: absolute;
      width: 64px;
      left: 0px;
      height: 48px;
      transform-style: preserve-3d;
      top: 48px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-vjmi {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 64px;
      transform-style: preserve-3d;
      top: 48px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-12v2 {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 128px;
      transform-style: preserve-3d;
      top: 48px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-16p9 {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 192px;
      transform-style: preserve-3d;
      top: 48px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-rht6 {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 256px;
      transform-style: preserve-3d;
      top: 48px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-12q6 {
      position: absolute;
      width: 64px;
      left: 0px;
      height: 48px;
      transform-style: preserve-3d;
      top: 96px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-43or {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 64px;
      transform-style: preserve-3d;
      top: 96px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-az0z {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 128px;
      transform-style: preserve-3d;
      top: 96px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-11om {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 192px;
      transform-style: preserve-3d;
      top: 96px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-91vl {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 256px;
      transform-style: preserve-3d;
      top: 96px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-pk6a {
      position: absolute;
      width: 64px;
      left: 0px;
      height: 48px;
      transform-style: preserve-3d;
      top: 144px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-10zm {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 64px;
      transform-style: preserve-3d;
      top: 144px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-1pdp {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 128px;
      transform-style: preserve-3d;
      top: 144px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-16oz {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 192px;
      transform-style: preserve-3d;
      top: 144px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-vvt0 {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 256px;
      transform-style: preserve-3d;
      top: 144px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-1j55 {
      position: absolute;
      width: 64px;
      left: 0px;
      height: 48px;
      transform-style: preserve-3d;
      top: 192px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-2vxf {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 64px;
      transform-style: preserve-3d;
      top: 192px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-1g82 {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 128px;
      transform-style: preserve-3d;
      top: 192px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-pn00 {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 192px;
      transform-style: preserve-3d;
      top: 192px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-qqdj {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 256px;
      transform-style: preserve-3d;
      top: 192px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-4r4q {
      position: absolute;
      width: 64px;
      left: 0px;
      height: 48px;
      transform-style: preserve-3d;
      top: 240px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-yybc {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 64px;
      transform-style: preserve-3d;
      top: 240px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-1wos {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 128px;
      transform-style: preserve-3d;
      top: 240px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-1f2k {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 192px;
      transform-style: preserve-3d;
      top: 240px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-oo34 {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 256px;
      transform-style: preserve-3d;
      top: 240px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-1ji9 {
      position: absolute;
      width: 64px;
      left: 0px;
      height: 48px;
      transform-style: preserve-3d;
      top: 288px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-i7rd {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 64px;
      transform-style: preserve-3d;
      top: 288px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-cl3e {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 128px;
      transform-style: preserve-3d;
      top: 288px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-1733 {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 192px;
      transform-style: preserve-3d;
      top: 288px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-jshp {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 256px;
      transform-style: preserve-3d;
      top: 288px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-p09s {
      position: absolute;
      width: 64px;
      left: 0px;
      height: 48px;
      transform-style: preserve-3d;
      top: 336px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-snqw {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 64px;
      transform-style: preserve-3d;
      top: 336px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-2qnx {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 128px;
      transform-style: preserve-3d;
      top: 336px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-o9jy {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 192px;
      transform-style: preserve-3d;
      top: 336px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-1rog {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 256px;
      transform-style: preserve-3d;
      top: 336px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-7xzr {
      position: absolute;
      width: 64px;
      left: 0px;
      height: 48px;
      transform-style: preserve-3d;
      top: 384px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-29yz {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 64px;
      transform-style: preserve-3d;
      top: 384px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-1y3j {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 128px;
      transform-style: preserve-3d;
      top: 384px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-1s5c {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 192px;
      transform-style: preserve-3d;
      top: 384px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-13xn {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 256px;
      transform-style: preserve-3d;
      top: 384px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-y35r {
      position: absolute;
      width: 64px;
      left: 0px;
      height: 48px;
      transform-style: preserve-3d;
      top: 432px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-iw1v {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 64px;
      transform-style: preserve-3d;
      top: 432px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-1opa {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 128px;
      transform-style: preserve-3d;
      top: 432px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-c78x {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 192px;
      transform-style: preserve-3d;
      top: 432px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] .gwd-grp-834h.gwd-img-1j97 {
      position: absolute;
      width: 64px;
      height: 48px;
      left: 256px;
      transform-style: preserve-3d;
      top: 432px;
      transform: translate3d(0px, 0px, 0px);
    }
    [data-gwd-group="animation-group-p"] {
      width: 320px;
      height: 480px;
    }
    .gwd-div-6mbx {
      position: absolute;
      left: 0px;
      top: 0px;
    }
    .gwd-div-13xq {
      position: absolute;
      width: 320px;
      font-family: Roboto;
      font-size: 18px;
      text-align: center;
      height: 26px;
      color: rgb(233, 233, 233);
      top: 227px;
      left: 0px;
    }
    .gwd-taparea-13k2 {
      position: absolute;
      width: 300px;
      height: 250px;
      top: 115px;
      left: 10px;
    }
    .gwd-img-1oxl {
      position: absolute;
      left: 0px;
      top: 0px;
      width: 320px;
      height: 480px;
    }
    .gwd-div-eo6l {
      position: absolute;
      opacity: 0.5;
      top: 0px;
      width: 480px;
      height: 320px;
      left: 0px;
      background-image: none;
      background-color: rgb(0, 0, 0);
    }
    .gwd-div-1pzo {
      width: 480px;
      height: 320px;
    }
    .gwd-div-14y6 {
      width: 480px;
      height: 320px;
    }
    .gwd-div-cyj4 {
      position: absolute;
      width: 320px;
      font-family: Roboto;
      font-size: 18px;
      text-align: center;
      height: 26px;
      color: rgb(233, 233, 233);
      top: 147px;
      left: 80px;
    }
    .gwd-taparea-1cwh {
      width: 300px;
      height: 250px;
      position: absolute;
      top: 35px;
      left: 90px;
    }
    .gwd-img-43t3 {
      width: 480px;
      height: 320px;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-s9v4 {
      position: absolute;
      width: 96px;
      height: 64px;
      left: 0px;
      top: 0px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-6xd3 {
      position: absolute;
      height: 64px;
      left: 96px;
      width: 96px;
      top: 0px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-186s {
      position: absolute;
      height: 64px;
      width: 96px;
      left: 192px;
      top: 0px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-v8gd {
      position: absolute;
      height: 64px;
      width: 96px;
      left: 288px;
      top: 0px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-1dtr {
      position: absolute;
      width: 96px;
      height: 64px;
      left: 384px;
      top: 0px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-ue35 {
      position: absolute;
      width: 96px;
      left: 0px;
      height: 64px;
      top: 64px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-130p {
      position: absolute;
      width: 96px;
      height: 64px;
      left: 96px;
      top: 64px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-1r5v {
      position: absolute;
      width: 96px;
      height: 64px;
      left: 192px;
      top: 64px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-x8sf {
      position: absolute;
      width: 96px;
      height: 64px;
      left: 288px;
      top: 64px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-g4yb {
      position: absolute;
      width: 96px;
      height: 64px;
      left: 384px;
      top: 64px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-1er1 {
      position: absolute;
      width: 96px;
      height: 64px;
      left: 0px;
      top: 128px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-1o10 {
      position: absolute;
      width: 96px;
      height: 64px;
      left: 96px;
      top: 128px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-iwso {
      position: absolute;
      width: 96px;
      height: 64px;
      left: 192px;
      top: 128px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-v6qm {
      position: absolute;
      width: 96px;
      height: 64px;
      left: 288px;
      top: 128px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-1z0y {
      position: absolute;
      width: 96px;
      height: 64px;
      left: 384px;
      top: 128px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-1q5u {
      position: absolute;
      height: 64px;
      width: 96px;
      left: 0px;
      top: 192px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-la9n {
      position: absolute;
      width: 96px;
      height: 64px;
      left: 96px;
      top: 192px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-1sk3 {
      position: absolute;
      width: 96px;
      height: 64px;
      left: 192px;
      top: 192px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-cau2 {
      position: absolute;
      width: 96px;
      height: 64px;
      left: 288px;
      top: 192px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-1ot9 {
      position: absolute;
      width: 96px;
      height: 64px;
      left: 384px;
      top: 192px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-vhcg {
      position: absolute;
      width: 96px;
      height: 64px;
      left: 0px;
      top: 256px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-1aax {
      position: absolute;
      width: 96px;
      height: 64px;
      left: 96px;
      top: 256px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-111z {
      position: absolute;
      width: 96px;
      height: 64px;
      left: 192px;
      top: 256px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-33ec {
      position: absolute;
      width: 96px;
      height: 64px;
      left: 288px;
      top: 256px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] .gwd-grp-9fox.gwd-img-145y {
      position: absolute;
      width: 96px;
      height: 64px;
      left: 384px;
      top: 256px;
      transform-style: preserve-3d;
    }
    [data-gwd-group="animation-group-l"] {
      width: 480px;
      height: 320px;
    }
    .gwd-div-rxwe {
      position: absolute;
      left: 0px;
      top: 0px;
    }
    .gwd-div-9q9e {
      width: 480px;
      height: 320px;
    }
    .gwd-div-1ua0 {
      width: 480px;
      height: 320px;
    }
    .gwd-img-a027 {
      position: absolute;
      left: 23px;
      top: 13px;
      width: 96px;
      height: 96px;
    }
    .gwd-div-1prl {
      position: absolute;
      text-align: left;
      left: 124px;
      font-family: Roboto;
      color: rgb(255, 255, 255);
      display: block;
      white-space: nowrap;
      overflow-x: hidden;
      -webkit-mask: -webkit-linear-gradient(left, rgb(0, 0, 0), rgb(0, 0, 0) 78%, rgba(0, 0, 0, 0) 95%);
      opacity: 1;
      width: 245px;
      font-size: 18px;
      height: 25px;
      top: 18px;
    }
    .gwd-taparea-m3xh {
      position: absolute;
      width: 100px;
      height: 30px;
      left: 370px;
      top: 29px;
    }
    .gwd-starratings-g5xd {
      position: absolute;
      width: 100px;
      height: 20px;
      left: 124px;
      top: 44px;
    }
    .gwd-carouselgallery-1lw8 {
      position: absolute;
      left: 0px;
      width: 480px;
      height: 206px;
      top: 114px;
    }
    .gwd-div-mjvo {
      position: absolute;
      text-align: left;
      width: 80px;
      color: rgb(68, 128, 246);
      font-family: roboto;
      font-size: 14px;
      height: 18px;
      left: 225px;
      top: 45px;
    }
    .gwd-img-6udd {
      position: absolute;
      width: 100px;
      height: 31px;
      left: 0px;
      top: 0px;
    }
    .gwd-div-x2lz {
      position: absolute;
      width: 100px;
      text-align: center;
      font-family: Roboto;
      left: 0px;
      color: rgb(255, 255, 255);
      height: 20px;
      top: 5px;
    }
    .gwd-div-136e {
      position: absolute;
      text-align: left;
      color: rgb(255, 255, 255);
      font-family: Roboto;
      font-size: 16px;
      height: 18px;
      left: 124px;
      top: 93px;
      width: 356px;
    }
    .gwd-img-12kx {
      position: absolute;
      width: 480px;
      left: 0px;
      height: 320px;
      top: 0px;
    }
    .gwd-div-1ag3 {
      position: absolute;
      font-family: "Times New Roman";
      text-align: left;
      color: rgb(0, 0, 0);
      width: 102px;
      height: 23px;
      left: 189px;
      top: 289px;
    }
    .gwd-div-1k8j {
      position: absolute;
      width: 102px;
      height: 23px;
      opacity: 0.5;
      margin: 0px;
      border-radius: 12px;
      left: 0px;
      top: 0px;
      background-image: none;
      background-color: rgb(45, 45, 45);
    }
    .gwd-gallerynavigation-11t7 {
      position: absolute;
      width: 102px;
      height: 23px;
      top: 0px;
      left: 0px;
    }
    .gwd-div-1kn6 {
      width: 320px;
      height: 480px;
    }
    .gwd-div-1cau {
      width: 320px;
      height: 480px;
    }
    .gwd-img-3a63 {
      position: absolute;
      left: 0px;
      top: 0px;
      width: 320px;
      height: 480px;
    }
    .gwd-img-1pqe {
      position: absolute;
      left: 20px;
      top: 20px;
      width: 96px;
      height: 96px;
    }
    .gwd-taparea-4q4d {
      position: absolute;
      left: 110px;
      top: 210px;
      width: 100px;
      height: 30px;
    }
    .gwd-div-1pjh {
      position: absolute;
      text-align: left;
      left: 124px;
      top: 38px;
      color: rgb(255, 255, 255);
      font-family: Roboto;
      font-size: 18px;
      width: 195px;
      display: block;
      white-space: nowrap;
      overflow-x: hidden;
      -webkit-mask: -webkit-linear-gradient(left, rgb(0, 0, 0), rgb(0, 0, 0) 78%, rgba(0, 0, 0, 0) 95%);
      opacity: 1;
      height: 27px;
    }
    .gwd-starratings-1m7u {
      position: absolute;
      left: 124px;
      height: 20px;
      top: 66px;
      width: 96px;
    }
    .gwd-div-1dn9 {
      position: absolute;
      left: 224px;
      text-align: left;
      color: rgb(68, 128, 246);
      font-family: Roboto;
      font-size: 14px;
      height: 19px;
      width: 96px;
      top: 67px;
    }
    .gwd-carouselgallery-70vd {
      position: absolute;
      width: 320px;
      height: 220px;
      left: 0px;
      top: 241px;
    }
    .gwd-div-1qh9 {
      position: absolute;
      text-align: left;
      top: 124px;
      color: rgb(255, 255, 255);
      font-family: Roboto;
      height: 22px;
      left: 23px;
      width: 274px;
    }
    .gwd-div-kvkc {
      position: absolute;
      text-align: left;
      height: 42px;
      color: rgb(255, 255, 255);
      font-family: Roboto;
      font-size: 14px;
      top: 147px;
      left: 23px;
      width: 274px;
      background-image: none;
    }
    .gwd-div-gpa7 {
      position: absolute;
      height: 23px;
      width: 102px;
      left: 110px;
      top: 449px;
    }
    .gwd-div-9n3c {
      position: absolute;
      left: 0px;
      top: 0px;
      width: 102px;
      height: 23px;
      border-radius: 12px;
      opacity: 0.5;
      background-image: none;
      background-color: rgb(226, 226, 226);
    }
    .gwd-gallerynavigation-1xi0 {
      position: absolute;
      height: 23px;
      left: 0px;
      top: 0px;
      width: 102px;
    }
    .gwd-img-17hz {
      position: absolute;
      left: 0px;
      width: 100px;
      height: 30px;
      top: 0px;
    }
    .gwd-div-2vxp {
      position: absolute;
      color: rgb(255, 255, 255);
      font-family: Roboto;
      width: 89px;
      height: 21px;
      left: 6px;
      top: 5px;
      text-align: center;
    }
    .gwd-div-yoyg {
      text-align: center;
    }
    .gwd-div-2hgu {
      position: absolute;
      width: 278px;
      text-align: left;
      color: rgb(255, 255, 255);
      font-family: Roboto;
      height: 20px;
      left: 124px;
      top: 70px;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-crl4gwdanimation {
      animation: 2.2s linear 0s 1 normal forwards running gwd-gen-crl4gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-115agwdanimation {
      animation: 2.1s linear 0s 1 normal forwards running gwd-gen-115agwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-ik1kgwdanimation {
      animation: 2.2s linear 0s 1 normal forwards running gwd-gen-ik1kgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-tq6pgwdanimation {
      animation: 2.3s linear 0s 1 normal forwards running gwd-gen-tq6pgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-s2tpgwdanimation {
      animation: 2.2s linear 0s 1 normal forwards running gwd-gen-s2tpgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-1mp6gwdanimation {
      animation: 2.1s linear 0s 1 normal forwards running gwd-gen-1mp6gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-fi20gwdanimation {
      animation: 2s linear 0s 1 normal forwards running gwd-gen-fi20gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-1wasgwdanimation {
      animation: 2.1s linear 0s 1 normal forwards running gwd-gen-1wasgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-1n09gwdanimation {
      animation: 2s linear 0s 1 normal forwards running gwd-gen-1n09gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-1b3agwdanimation {
      animation: 1.8s linear 0s 1 normal forwards running gwd-gen-1b3agwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-1sw1gwdanimation {
      animation: 2.1s linear 0s 1 normal forwards running gwd-gen-1sw1gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-k076gwdanimation {
      animation: 2.2s linear 0s 1 normal forwards running gwd-gen-k076gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-rtv5gwdanimation {
      animation: 2s linear 0s 1 normal forwards running gwd-gen-rtv5gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-1qmwgwdanimation {
      animation: 2.1s linear 0s 1 normal forwards running gwd-gen-1qmwgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-5no4gwdanimation {
      animation: 2s linear 0s 1 normal forwards running gwd-gen-5no4gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-1eu0gwdanimation {
      animation: 1.9s linear 0s 1 normal forwards running gwd-gen-1eu0gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-15lhgwdanimation {
      animation: 1.7s linear 0s 1 normal forwards running gwd-gen-15lhgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-16z7gwdanimation {
      animation: 2.2s linear 0s 1 normal forwards running gwd-gen-16z7gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-c1swgwdanimation {
      animation: 2.1s linear 0s 1 normal forwards running gwd-gen-c1swgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-10gtgwdanimation {
      animation: 2.3s linear 0s 1 normal forwards running gwd-gen-10gtgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-1g5wgwdanimation {
      animation: 2.2s linear 0s 1 normal forwards running gwd-gen-1g5wgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-1owigwdanimation {
      animation: 2.1s linear 0s 1 normal forwards running gwd-gen-1owigwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-q2fygwdanimation {
      animation: 2.2s linear 0s 1 normal forwards running gwd-gen-q2fygwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-yc66gwdanimation {
      animation: 2s linear 0s 1 normal forwards running gwd-gen-yc66gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-1aimgwdanimation {
      animation: 2.1s linear 0s 1 normal forwards running gwd-gen-1aimgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-twukgwdanimation {
      animation: 2s linear 0s 1 normal forwards running gwd-gen-twukgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-x3u1gwdanimation {
      animation: 2.3s linear 0s 1 normal forwards running gwd-gen-x3u1gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-b7u2gwdanimation {
      animation: 2.2s linear 0s 1 normal forwards running gwd-gen-b7u2gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-1wctgwdanimation {
      animation: 2.1s linear 0s 1 normal forwards running gwd-gen-1wctgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-pzjggwdanimation {
      animation: 2s linear 0s 1 normal forwards running gwd-gen-pzjggwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-1i50gwdanimation {
      animation: 1.9s linear 0s 1 normal forwards running gwd-gen-1i50gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-1g9lgwdanimation {
      animation: 2s linear 0s 1 normal forwards running gwd-gen-1g9lgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-4m7qgwdanimation {
      animation: 1.8s linear 0s 1 normal forwards running gwd-gen-4m7qgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-1lbugwdanimation {
      animation: 1.7s linear 0s 1 normal forwards running gwd-gen-1lbugwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-171egwdanimation {
      animation: 2.2s linear 0s 1 normal forwards running gwd-gen-171egwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-1ewmgwdanimation {
      animation: 1.9s linear 0s 1 normal forwards running gwd-gen-1ewmgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-z1uegwdanimation {
      animation: 1.7s linear 0s 1 normal forwards running gwd-gen-z1uegwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-nqalgwdanimation {
      animation: 2s linear 0s 1 normal forwards running gwd-gen-nqalgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-cs8rgwdanimation {
      animation: 2.3s linear 0s 1 normal forwards running gwd-gen-cs8rgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-laaogwdanimation {
      animation: 1.9s linear 0s 1 normal forwards running gwd-gen-laaogwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-1s2ogwdanimation {
      animation: 2s linear 0s 1 normal forwards running gwd-gen-1s2ogwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-snoegwdanimation {
      animation: 1.9s linear 0s 1 normal forwards running gwd-gen-snoegwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-u54cgwdanimation {
      animation: 2.1s linear 0s 1 normal forwards running gwd-gen-u54cgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-6mglgwdanimation {
      animation: 1.7s linear 0s 1 normal forwards running gwd-gen-6mglgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-ea81gwdanimation {
      animation: 2s linear 0s 1 normal forwards running gwd-gen-ea81gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-1ttxgwdanimation {
      animation: 2.1s linear 0s 1 normal forwards running gwd-gen-1ttxgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-1eaigwdanimation {
      animation: 2s linear 0s 1 normal forwards running gwd-gen-1eaigwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-1etvgwdanimation {
      animation: 2.1s linear 0s 1 normal forwards running gwd-gen-1etvgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-uij2gwdanimation {
      animation: 1.9s linear 0s 1 normal forwards running gwd-gen-uij2gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-p"] .gwd-gen-lajlgwdanimation {
      animation: 2s linear 0s 1 normal forwards running gwd-gen-lajlgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-1ba7gwdanimation {
      animation: 2s linear 0s 1 normal forwards running gwd-gen-1ba7gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-d63ngwdanimation {
      animation: 2s linear 0s 1 normal forwards running gwd-gen-d63ngwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-tga0gwdanimation {
      animation: 2s linear 0s 1 normal forwards running gwd-gen-tga0gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-1g66gwdanimation {
      animation: 2s linear 0s 1 normal forwards running gwd-gen-1g66gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-1gcpgwdanimation {
      animation: 2s linear 0s 1 normal forwards running gwd-gen-1gcpgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-1ankgwdanimation {
      animation: 2s linear 0s 1 normal forwards running gwd-gen-1ankgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-148tgwdanimation {
      animation: 2s linear 0s 1 normal forwards running gwd-gen-148tgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-1ee1gwdanimation {
      animation: 2s linear 0s 1 normal forwards running gwd-gen-1ee1gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-w7sigwdanimation {
      animation: 1.9s linear 0s 1 normal forwards running gwd-gen-w7sigwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-19jzgwdanimation {
      animation: 2.1s linear 0s 1 normal forwards running gwd-gen-19jzgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-144rgwdanimation {
      animation: 2.1s linear 0s 1 normal forwards running gwd-gen-144rgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-1x8cgwdanimation {
      animation: 1.7s linear 0s 1 normal forwards running gwd-gen-1x8cgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-evc7gwdanimation {
      animation: 2.1s linear 0s 1 normal forwards running gwd-gen-evc7gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-1wn3gwdanimation {
      animation: 1.9s linear 0s 1 normal forwards running gwd-gen-1wn3gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-k64agwdanimation {
      animation: 1.9s linear 0s 1 normal forwards running gwd-gen-k64agwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-iurygwdanimation {
      animation: 2.4s linear 0s 1 normal forwards running gwd-gen-iurygwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-7glzgwdanimation {
      animation: 1.7s linear 0s 1 normal forwards running gwd-gen-7glzgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-a805gwdanimation {
      animation: 1.9s linear 0s 1 normal forwards running gwd-gen-a805gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-1ob8gwdanimation {
      animation: 2.2s linear 0s 1 normal forwards running gwd-gen-1ob8gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-b2w9gwdanimation {
      animation: 1.7s linear 0s 1 normal forwards running gwd-gen-b2w9gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-1x2lgwdanimation {
      animation: 1.8s linear 0s 1 normal forwards running gwd-gen-1x2lgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-1ss7gwdanimation {
      animation: 1.9s linear 0s 1 normal forwards running gwd-gen-1ss7gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-1491gwdanimation {
      animation: 2.1s linear 0s 1 normal forwards running gwd-gen-1491gwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-19sjgwdanimation {
      animation: 2.2s linear 0s 1 normal forwards running gwd-gen-19sjgwdanimation_gwd-keyframes;
    }
    .gwd-play-animation [data-gwd-group="animation-group-l"] .gwd-gen-1psmgwdanimation {
      animation: 2.3s linear 0s 1 normal forwards running gwd-gen-1psmgwdanimation_gwd-keyframes;
    ruby-merge: domain; 
    } 

    @keyframes gwd-gen-lajlgwdanimation_gwd-keyframes {
      0% {
        top: 0px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      50% {
        top: 0px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 480px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-uij2gwdanimation_gwd-keyframes {
      0% {
        top: 0px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      52.63% {
        top: 0px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 480px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1etvgwdanimation_gwd-keyframes {
      0% {
        top: 0px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      47.62% {
        top: 0px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 480px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1eaigwdanimation_gwd-keyframes {
      0% {
        top: 0px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      50% {
        top: 0px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 480px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1ttxgwdanimation_gwd-keyframes {
      0% {
        top: 0px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      47.62% {
        top: 0px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 480px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-ea81gwdanimation_gwd-keyframes {
      0% {
        top: 48px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      50% {
        top: 48px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 500px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-6mglgwdanimation_gwd-keyframes {
      0% {
        top: 48px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      58.82% {
        top: 48px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 500px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-u54cgwdanimation_gwd-keyframes {
      0% {
        top: 48px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      47.62% {
        top: 48px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 500px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-snoegwdanimation_gwd-keyframes {
      0% {
        top: 48px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      52.63% {
        top: 48px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 500px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1s2ogwdanimation_gwd-keyframes {
      0% {
        top: 48px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      50% {
        top: 48px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 500px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-laaogwdanimation_gwd-keyframes {
      0% {
        top: 96px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      52.63% {
        top: 96px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 520px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-cs8rgwdanimation_gwd-keyframes {
      0% {
        top: 96px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      43.48% {
        top: 96px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 520px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-nqalgwdanimation_gwd-keyframes {
      0% {
        top: 96px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      50% {
        top: 96px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 520px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-z1uegwdanimation_gwd-keyframes {
      0% {
        top: 96px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      58.82% {
        top: 96px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 520px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1ewmgwdanimation_gwd-keyframes {
      0% {
        top: 96px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      52.63% {
        top: 96px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 520px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-171egwdanimation_gwd-keyframes {
      0% {
        top: 144px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      45.45% {
        top: 144px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 540px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1lbugwdanimation_gwd-keyframes {
      0% {
        top: 144px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      58.82% {
        top: 144px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 540px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-4m7qgwdanimation_gwd-keyframes {
      0% {
        top: 144px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      55.56% {
        top: 144px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 540px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1g9lgwdanimation_gwd-keyframes {
      0% {
        top: 144px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      50% {
        top: 144px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 540px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1i50gwdanimation_gwd-keyframes {
      0% {
        top: 144px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      52.63% {
        top: 144px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 540px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-pzjggwdanimation_gwd-keyframes {
      0% {
        top: 192px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      50% {
        top: 192px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 560px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1wctgwdanimation_gwd-keyframes {
      0% {
        top: 192px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      47.62% {
        top: 192px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 560px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-b7u2gwdanimation_gwd-keyframes {
      0% {
        top: 192px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      45.45% {
        top: 192px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 560px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-x3u1gwdanimation_gwd-keyframes {
      0% {
        top: 192px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      43.48% {
        top: 192px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 560px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-twukgwdanimation_gwd-keyframes {
      0% {
        top: 192px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      50% {
        top: 192px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 560px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1aimgwdanimation_gwd-keyframes {
      0% {
        top: 240px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      47.62% {
        top: 240px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 580px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-yc66gwdanimation_gwd-keyframes {
      0% {
        top: 240px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      50% {
        top: 240px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        top: 580px;
        transform: translate3d(0px, 580px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-q2fygwdanimation_gwd-keyframes {
      0% {
        top: 240px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      45.45% {
        top: 240px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        top: 580px;
        transform: translate3d(0px, 580px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1owigwdanimation_gwd-keyframes {
      0% {
        top: 240px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      47.62% {
        top: 240px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 580px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1g5wgwdanimation_gwd-keyframes {
      0% {
        top: 240px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      45.45% {
        top: 240px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 580px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-10gtgwdanimation_gwd-keyframes {
      0% {
        top: 288px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      43.48% {
        top: 288px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 600px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-c1swgwdanimation_gwd-keyframes {
      0% {
        top: 288px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      47.62% {
        top: 288px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 600px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-16z7gwdanimation_gwd-keyframes {
      0% {
        top: 288px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      45.45% {
        top: 288px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 600px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-15lhgwdanimation_gwd-keyframes {
      0% {
        top: 288px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      58.82% {
        top: 288px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 600px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1eu0gwdanimation_gwd-keyframes {
      0% {
        top: 288px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      52.63% {
        top: 288px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 600px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-5no4gwdanimation_gwd-keyframes {
      0% {
        top: 336px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      50% {
        top: 336px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 620px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1qmwgwdanimation_gwd-keyframes {
      0% {
        top: 336px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      47.62% {
        top: 336px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 620px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-rtv5gwdanimation_gwd-keyframes {
      0% {
        top: 336px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      50% {
        top: 336px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 620px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-k076gwdanimation_gwd-keyframes {
      0% {
        top: 336px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      45.45% {
        top: 336px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 620px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1sw1gwdanimation_gwd-keyframes {
      0% {
        top: 336px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      47.62% {
        top: 336px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 620px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1b3agwdanimation_gwd-keyframes {
      0% {
        top: 384px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      55.56% {
        top: 384px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 640px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1n09gwdanimation_gwd-keyframes {
      0% {
        top: 384px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      50% {
        top: 384px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 640px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1wasgwdanimation_gwd-keyframes {
      0% {
        top: 384px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      47.62% {
        top: 384px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 640px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-fi20gwdanimation_gwd-keyframes {
      0% {
        top: 384px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      50% {
        top: 384px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 640px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1mp6gwdanimation_gwd-keyframes {
      0% {
        top: 384px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      47.62% {
        top: 384px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 640px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-s2tpgwdanimation_gwd-keyframes {
      0% {
        top: 432px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      45.45% {
        top: 432px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 660px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-tq6pgwdanimation_gwd-keyframes {
      0% {
        top: 432px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      43.48% {
        top: 432px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 660px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-ik1kgwdanimation_gwd-keyframes {
      0% {
        top: 432px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      45.45% {
        top: 432px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 660px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-115agwdanimation_gwd-keyframes {
      0% {
        top: 432px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      47.62% {
        top: 432px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 660px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-crl4gwdanimation_gwd-keyframes {
      0% {
        top: 432px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      45.45% {
        top: 432px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: ease-in;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 660px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1ba7gwdanimation_gwd-keyframes {
      0% {
        left: 0px;
        top: 0px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      50% {
        left: 0px;
        top: 0px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        left: 0px;
        top: 0px;
        transform: translate3d(0px, 560px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1psmgwdanimation_gwd-keyframes {
      0% {
        top: 0px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      43.48% {
        top: 0px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 560px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-19sjgwdanimation_gwd-keyframes {
      0% {
        left: 192px;
        top: 0px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      45.45% {
        left: 192px;
        top: 0px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        left: 192px;
        top: 0px;
        transform: translate3d(0px, 560px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1491gwdanimation_gwd-keyframes {
      0% {
        left: 288px;
        top: 0px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      47.62% {
        left: 288px;
        top: 0px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        left: 288px;
        top: 0px;
        transform: translate3d(0px, 560px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-d63ngwdanimation_gwd-keyframes {
      0% {
        left: 384px;
        top: 0px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      50% {
        left: 384px;
        top: 0px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        left: 384px;
        top: 0px;
        transform: translate3d(0px, 560px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1ss7gwdanimation_gwd-keyframes {
      0% {
        top: 64px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      52.63% {
        top: 64px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        top: 0px;
        transform: translate3d(0px, 540px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-tga0gwdanimation_gwd-keyframes {
      0% {
        left: 96px;
        top: 64px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      50% {
        left: 96px;
        top: 64px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        left: 96px;
        top: 0px;
        transform: translate3d(0px, 540px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1x2lgwdanimation_gwd-keyframes {
      0% {
        left: 192px;
        top: 64px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      55.56% {
        left: 192px;
        top: 64px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        left: 192px;
        top: 0px;
        transform: translate3d(0px, 540px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-b2w9gwdanimation_gwd-keyframes {
      0% {
        left: 288px;
        top: 64px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      58.82% {
        left: 288px;
        top: 64px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        left: 288px;
        top: 0px;
        transform: translate3d(0px, 540px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1ob8gwdanimation_gwd-keyframes {
      0% {
        left: 384px;
        top: 64px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      45.45% {
        left: 384px;
        top: 64px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        left: 384px;
        top: 0px;
        transform: translate3d(0px, 540px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-a805gwdanimation_gwd-keyframes {
      0% {
        left: 0px;
        top: 128px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      52.63% {
        left: 0px;
        top: 128px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        left: 0px;
        top: 0px;
        transform: translate3d(0px, 540px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-7glzgwdanimation_gwd-keyframes {
      0% {
        left: 96px;
        top: 128px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      58.82% {
        left: 96px;
        top: 128px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        left: 96px;
        top: 0px;
        transform: translate3d(0px, 540px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1g66gwdanimation_gwd-keyframes {
      0% {
        left: 192px;
        top: 128px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      50% {
        left: 192px;
        top: 128px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        left: 192px;
        top: 0px;
        transform: translate3d(0px, 540px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-iurygwdanimation_gwd-keyframes {
      0% {
        left: 288px;
        top: 128px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      41.67% {
        left: 288px;
        top: 128px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        left: 288px;
        top: 0px;
        transform: translate3d(0px, 540px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-k64agwdanimation_gwd-keyframes {
      0% {
        left: 384px;
        top: 128px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      52.63% {
        left: 384px;
        top: 128px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        left: 384px;
        top: 0px;
        transform: translate3d(0px, 540px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1gcpgwdanimation_gwd-keyframes {
      0% {
        left: 0px;
        top: 192px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      50% {
        left: 0px;
        top: 192px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        left: 0px;
        top: 0px;
        transform: translate3d(0px, 500px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1wn3gwdanimation_gwd-keyframes {
      0% {
        left: 96px;
        top: 192px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      52.63% {
        left: 96px;
        top: 192px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        left: 96px;
        top: 0px;
        transform: translate3d(0px, 500px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-evc7gwdanimation_gwd-keyframes {
      0% {
        left: 192px;
        top: 192px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      47.62% {
        left: 192px;
        top: 192px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        left: 192px;
        top: 0px;
        transform: translate3d(0px, 500px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1x8cgwdanimation_gwd-keyframes {
      0% {
        left: 288px;
        top: 192px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      58.82% {
        left: 288px;
        top: 192px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        left: 288px;
        top: 0px;
        transform: translate3d(0px, 500px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1ankgwdanimation_gwd-keyframes {
      0% {
        left: 384px;
        top: 192px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      50% {
        left: 384px;
        top: 192px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        left: 384px;
        top: 0px;
        transform: translate3d(0px, 500px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-144rgwdanimation_gwd-keyframes {
      0% {
        left: 0px;
        top: 256px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      47.62% {
        left: 0px;
        top: 256px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        left: 0px;
        top: 0px;
        transform: translate3d(0px, 480px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-148tgwdanimation_gwd-keyframes {
      0% {
        left: 96px;
        top: 256px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      50% {
        left: 96px;
        top: 256px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        left: 96px;
        top: 0px;
        transform: translate3d(0px, 480px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-19jzgwdanimation_gwd-keyframes {
      0% {
        left: 192px;
        top: 256px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      47.62% {
        left: 192px;
        top: 256px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        left: 192px;
        top: 0px;
        transform: translate3d(0px, 480px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-w7sigwdanimation_gwd-keyframes {
      0% {
        left: 288px;
        top: 256px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      52.63% {
        left: 288px;
        top: 256px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        left: 288px;
        top: 0px;
        transform: translate3d(0px, 480px, 0px);
        animation-timing-function: ease-in;
      }
    }
    @keyframes gwd-gen-1ee1gwdanimation_gwd-keyframes {
      0% {
        left: 384px;
        top: 256px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      50% {
        left: 384px;
        top: 256px;
        transform: translate3d(0px, 0px, 0px);
        animation-timing-function: linear;
      }
      100% {
        left: 384px;
        top: 0px;
        transform: translate3d(0px, 480px, 0px);
        animation-timing-function: ease-in;
      }
    }
  </style>
  <script data-source="gwd_webcomponents_v1_min.js" data-version="2" data-exports-type="gwd_webcomponents_v1" src="gwd_webcomponents_v1_min.js"></script>
  <script data-source="https://s0.2mdn.net/ads/studio/Enabler.js" data-exports-type="gwd-google-ad" src="https://s0.2mdn.net/ads/studio/Enabler.js"></script>
  <script type="text/javascript" src="groups_runtime.min.1.0.js" gwd-groups-version="1.0"></script>
  <script type="text/javascript" src="gwdid.min.1.0.js" gwd-gwdid-version="1.0"></script>
  <script gwd-events="support" src="gwd-events-support.1.0.js"></script>
  <script gwd-events="handlers">
    gwd.auto_Deleet_test_tapareaAction = function(event) {
      // GWD Predefined Function
      gwd.actions.timeline.play('animation-group-p');
    };
    gwd.auto_Deleet_test_taparea_1Action = function(event) {
      // GWD Predefined Function
      gwd.actions.timeline.play('animation-group-l');
    };
    gwd.auto__Animation_group_lEvent_1 = function(event) {
      // GWD Predefined Function
      gwd.actions.timeline.pause(' animation-group-l');
    };
    gwd.auto__Animation_group_lEvent_2 = function(event) {
      // GWD Predefined Function
      gwd.actions.gwdGoogleAd.goToPage('gwd-ad', 'page1_2', 'fade', 1000, 'linear', 'top');
    };
    gwd.auto__Animation_groupEvent_3 = function(event) {
      // GWD Predefined Function
      gwd.actions.timeline.pause(' animation-group');
    };
    gwd.auto__Animation_groupEvent_4 = function(event) {
      // GWD Predefined Function
      gwd.actions.gwdGoogleAd.goToPage('gwd-ad', 'page1_3', 'none', 1000, 'linear', 'top');
    };
    gwd.auto_Page1Shake1 = function(event) {
      // GWD Predefined Function
      gwd.actions.timeline.play('animation-group-p');
    };
    gwd.auto_Page1_1Shake = function(event) {
      // GWD Predefined Function
      gwd.actions.timeline.play('animation-group-l');
    };
    gwd.auto__Animation_group_pEvent_3 = function(event) {
      // GWD Predefined Function
      gwd.actions.timeline.pause(' animation-group-p');
    };
    gwd.auto__Animation_group_pEvent_4 = function(event) {
      // GWD Predefined Function
      gwd.actions.gwdGoogleAd.goToPage('gwd-ad', 'page1_3', 'fade', 1000, 'linear', 'top');
    };
    gwd.auto_Cta_lAction = function(event) {
      // GWD Predefined Function
      gwd.actions.gwdGoogleAd.exit('gwd-ad', 'Exit-L', '', true, true);
    };
    gwd.auto_Cta_pAction = function(event) {
      // GWD Predefined Function
      gwd.actions.gwdGoogleAd.exit('gwd-ad', 'Exit-P', '', true, true);
    };
  </script>
  <script gwd-events="registration">
    // Support code for event handling in Google Web Designer
    // This script block is auto-generated. Please do not edit!
    gwd.actions.events.registerEventHandlers = function(event) {
      gwd.actions.events.addHandler('DELETE-desktop-test-taparea-p', 'action', gwd.auto_Deleet_test_tapareaAction, false);
      gwd.actions.events.addHandler('DELETE-desktop-test-taparea-l', 'action', gwd.auto_Deleet_test_taparea_1Action, false);
      gwd.actions.events.addHandler(' animation-group-l', 'event-1', gwd.auto__Animation_group_lEvent_1, false);
      gwd.actions.events.addHandler(' animation-group-l', 'event-2', gwd.auto__Animation_group_lEvent_2, false);
      gwd.actions.events.addHandler(' animation-group', 'event-3', gwd.auto__Animation_groupEvent_3, false);
      gwd.actions.events.addHandler(' animation-group', 'event-4', gwd.auto__Animation_groupEvent_4, false);
      gwd.actions.events.addHandler('page1', 'shake', gwd.auto_Page1Shake1, false);
      gwd.actions.events.addHandler('page1_1', 'shake', gwd.auto_Page1_1Shake, false);
      gwd.actions.events.addHandler(' animation-group-p', 'event-3', gwd.auto__Animation_group_pEvent_3, false);
      gwd.actions.events.addHandler(' animation-group-p', 'event-4', gwd.auto__Animation_group_pEvent_4, false);
      gwd.actions.events.addHandler('cta-l', 'action', gwd.auto_Cta_lAction, false);
      gwd.actions.events.addHandler('cta-p', 'action', gwd.auto_Cta_pAction, false);
      gwd.actions.timeline.captureAnimationEnd(document.body);
      gwd.actions.deviceShake.initialize();
    };
    gwd.actions.events.deregisterEventHandlers = function(event) {
      gwd.actions.events.removeHandler('DELETE-desktop-test-taparea-p', 'action', gwd.auto_Deleet_test_tapareaAction, false);
      gwd.actions.events.removeHandler('DELETE-desktop-test-taparea-l', 'action', gwd.auto_Deleet_test_taparea_1Action, false);
      gwd.actions.events.removeHandler(' animation-group-l', 'event-1', gwd.auto__Animation_group_lEvent_1, false);
      gwd.actions.events.removeHandler(' animation-group-l', 'event-2', gwd.auto__Animation_group_lEvent_2, false);
      gwd.actions.events.removeHandler(' animation-group', 'event-3', gwd.auto__Animation_groupEvent_3, false);
      gwd.actions.events.removeHandler(' animation-group', 'event-4', gwd.auto__Animation_groupEvent_4, false);
      gwd.actions.events.removeHandler('page1', 'shake', gwd.auto_Page1Shake1, false);
      gwd.actions.events.removeHandler('page1_1', 'shake', gwd.auto_Page1_1Shake, false);
      gwd.actions.events.removeHandler(' animation-group-p', 'event-3', gwd.auto__Animation_group_pEvent_3, false);
      gwd.actions.events.removeHandler(' animation-group-p', 'event-4', gwd.auto__Animation_group_pEvent_4, false);
      gwd.actions.events.removeHandler('cta-l', 'action', gwd.auto_Cta_lAction, false);
      gwd.actions.events.removeHandler('cta-p', 'action', gwd.auto_Cta_pAction, false);
      gwd.actions.timeline.releaseAnimationEnd(document.body);
      gwd.actions.deviceShake.dispose();
    };
    document.addEventListener("DOMContentLoaded", gwd.actions.events.registerEventHandlers);
    document.addEventListener("unload", gwd.actions.events.deregisterEventHandlers);
  </script>
  <script data-source="gwdpage_min.js" data-version="13" data-exports-type="gwd-page" src="gwdpage_min.js"></script>
  <script data-source="gwdpagedeck_min.js" data-version="14" data-exports-type="gwd-pagedeck" src="gwdpagedeck_min.js"></script>
  <script data-source="gwdgesture_min.js" data-version="7" data-exports-type="gwd-gesture" src="gwdgesture_min.js"></script>
  <script data-source="gwdimage_min.js" data-version="17" data-exports-type="gwd-image" src="gwdimage_min.js"></script>
  <script data-source="gwdgallerynavigation_min.js" data-version="8" data-exports-type="gwd-gallerynavigation" src="gwdgallerynavigation_min.js"></script>
  <script data-source="gwdcarouselgallery_min.js" data-version="25" data-exports-type="gwd-carouselgallery" src="gwdcarouselgallery_min.js"></script>
  <script data-source="gwdattached_min.js" data-version="2" data-exports-type="gwd-attached" src="gwdattached_min.js"></script>
  <script data-source="gwdtexthelper_min.js" data-version="18" data-exports-type="gwd-text-helper" src="gwdtexthelper_min.js"></script>
  <script data-source="gwddatabinder_min.js" data-version="14" data-exports-type="gwd-data-binder" src="gwddatabinder_min.js"></script>
  <script data-source="gwdgooglead_min.js" data-version="9" data-exports-type="gwd-google-ad" src="gwdgooglead_min.js"></script>
  <script data-source="gwdgpadataprovider_min.js" data-version="12" data-exports-type="gwd-gpa-data-provider" src="gwdgpadataprovider_min.js"></script>
  <script data-source="gwdstarratings_min.js" data-version="3" data-exports-type="gwd-starratings" src="gwdstarratings_min.js"></script>
  <script data-source="gwdtaparea_min.js" data-version="7" data-exports-type="gwd-taparea" src="gwdtaparea_min.js"></script>
  <script src="gwd-text-fitting.js" gwd-text-fitting-runtime=""></script>
</head>

<body>
  <template id="gwd-group-definitions">
    <div data-gwd-group-def="animation-group-p" data-gwd-group-class="gwd-grp-834h" style="display: none;">
      <gwd-image class="gwd-img-13vi gwd-grp-834h gwd-gen-lajlgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-1" bind-source="screenshot1"></gwd-image>
      <gwd-image class="gwd-img-ek5n gwd-grp-834h gwd-gen-uij2gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-2" bind-source="screenshot2"></gwd-image>
      <gwd-image class="gwd-img-1qnx gwd-grp-834h gwd-gen-1etvgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-3" bind-source="screenshot3"></gwd-image>
      <gwd-image class="gwd-img-wvbf gwd-grp-834h gwd-gen-1eaigwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-4" bind-source="screenshot4"></gwd-image>
      <gwd-image class="gwd-img-ttao gwd-grp-834h gwd-gen-1ttxgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-5" bind-source="screenshot1"></gwd-image>
      <gwd-image class="gwd-img-86di gwd-grp-834h gwd-gen-ea81gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-6" bind-source="screenshot2"></gwd-image>
      <gwd-image class="gwd-img-vjmi gwd-grp-834h gwd-gen-6mglgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-7" bind-source="screenshot1"></gwd-image>
      <gwd-image class="gwd-img-12v2 gwd-grp-834h gwd-gen-u54cgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-8" bind-source="screenshot2"></gwd-image>
      <gwd-image class="gwd-img-16p9 gwd-grp-834h gwd-gen-snoegwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-9" bind-source="screenshot3"></gwd-image>
      <gwd-image class="gwd-img-rht6 gwd-grp-834h gwd-gen-1s2ogwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-10" bind-source="screenshot4"></gwd-image>
      <gwd-image class="gwd-img-12q6 gwd-grp-834h gwd-gen-laaogwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-11" bind-source="screenshot1"></gwd-image>
      <gwd-image class="gwd-img-43or gwd-grp-834h gwd-gen-cs8rgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-12" bind-source="screenshot3"></gwd-image>
      <gwd-image class="gwd-img-az0z gwd-grp-834h gwd-gen-nqalgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-13" bind-source="screenshot4"></gwd-image>
      <gwd-image class="gwd-img-11om gwd-grp-834h gwd-gen-z1uegwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-14" bind-source="screenshot1"></gwd-image>
      <gwd-image class="gwd-img-91vl gwd-grp-834h gwd-gen-1ewmgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-15" bind-source="screenshot2"></gwd-image>
      <gwd-image class="gwd-img-pk6a gwd-grp-834h gwd-gen-171egwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-16" bind-source="screenshot3"></gwd-image>
      <gwd-image class="gwd-img-10zm gwd-grp-834h gwd-gen-1lbugwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-17" bind-source="screenshot4"></gwd-image>
      <gwd-image class="gwd-img-1pdp gwd-grp-834h gwd-gen-4m7qgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-18" bind-source="screenshot1"></gwd-image>
      <gwd-image class="gwd-img-16oz gwd-grp-834h gwd-gen-1g9lgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-19" bind-source="screenshot2"></gwd-image>
      <gwd-image class="gwd-img-vvt0 gwd-grp-834h gwd-gen-1i50gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-20" bind-source="screenshot3"></gwd-image>
      <gwd-image class="gwd-img-1j55 gwd-grp-834h gwd-gen-pzjggwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-21" bind-source="screenshot4"></gwd-image>
      <gwd-image class="gwd-img-2vxf gwd-grp-834h gwd-gen-1wctgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-22" bind-source="screenshot2"></gwd-image>
      <gwd-image class="gwd-img-1g82 gwd-grp-834h gwd-gen-b7u2gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-23" bind-source="screenshot3"></gwd-image>
      <gwd-image class="gwd-img-pn00 gwd-grp-834h gwd-gen-x3u1gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-24" bind-source="screenshot4"></gwd-image>
      <gwd-image class="gwd-img-qqdj gwd-grp-834h gwd-gen-twukgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-25" bind-source="screenshot1"></gwd-image>
      <gwd-image class="gwd-img-4r4q gwd-grp-834h gwd-gen-1aimgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-26" bind-source="screenshot2"></gwd-image>
      <gwd-image class="gwd-img-yybc gwd-grp-834h gwd-gen-yc66gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-27" bind-source="screenshot3"></gwd-image>
      <gwd-image class="gwd-img-1wos gwd-grp-834h gwd-gen-q2fygwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-28" bind-source="screenshot4"></gwd-image>
      <gwd-image class="gwd-img-1f2k gwd-grp-834h gwd-gen-1owigwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-29" bind-source="screenshot1"></gwd-image>
      <gwd-image class="gwd-img-oo34 gwd-grp-834h gwd-gen-1g5wgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-30" bind-source="screenshot2"></gwd-image>
      <gwd-image class="gwd-img-1ji9 gwd-grp-834h gwd-gen-10gtgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-31" bind-source="screenshot3"></gwd-image>
      <gwd-image class="gwd-img-i7rd gwd-grp-834h gwd-gen-c1swgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-32" bind-source="screenshot4"></gwd-image>
      <gwd-image class="gwd-img-cl3e gwd-grp-834h gwd-gen-16z7gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-33" bind-source="screenshot1"></gwd-image>
      <gwd-image class="gwd-img-1733 gwd-grp-834h gwd-gen-15lhgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-34" bind-source="screenshot2"></gwd-image>
      <gwd-image class="gwd-img-jshp gwd-grp-834h gwd-gen-1eu0gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-35" bind-source="screenshot3"></gwd-image>
      <gwd-image class="gwd-img-p09s gwd-grp-834h gwd-gen-5no4gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-36" bind-source="screenshot4"></gwd-image>
      <gwd-image class="gwd-img-snqw gwd-grp-834h gwd-gen-1qmwgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-37" bind-source="screenshot1"></gwd-image>
      <gwd-image class="gwd-img-2qnx gwd-grp-834h gwd-gen-rtv5gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-38" bind-source="screenshot2"></gwd-image>
      <gwd-image class="gwd-img-o9jy gwd-grp-834h gwd-gen-k076gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-39" bind-source="screenshot3"></gwd-image>
      <gwd-image class="gwd-img-1rog gwd-grp-834h gwd-gen-1sw1gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-40" bind-source="screenshot4"></gwd-image>
      <gwd-image class="gwd-img-7xzr gwd-grp-834h gwd-gen-1b3agwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-41" bind-source="screenshot1"></gwd-image>
      <gwd-image class="gwd-img-29yz gwd-grp-834h gwd-gen-1n09gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-42" bind-source="screenshot2"></gwd-image>
      <gwd-image class="gwd-img-1y3j gwd-grp-834h gwd-gen-1wasgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-43" bind-source="screenshot3"></gwd-image>
      <gwd-image class="gwd-img-1s5c gwd-grp-834h gwd-gen-fi20gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-44" bind-source="screenshot4"></gwd-image>
      <gwd-image class="gwd-img-13xn gwd-grp-834h gwd-gen-1mp6gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-45" bind-source="screenshot1"></gwd-image>
      <gwd-image class="gwd-img-y35r gwd-grp-834h gwd-gen-s2tpgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-46" bind-source="screenshot2"></gwd-image>
      <gwd-image class="gwd-img-iw1v gwd-grp-834h gwd-gen-tq6pgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-47" bind-source="screenshot3"></gwd-image>
      <gwd-image class="gwd-img-1opa gwd-grp-834h gwd-gen-ik1kgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-48" bind-source="screenshot4"></gwd-image>
      <gwd-image class="gwd-img-c78x gwd-grp-834h gwd-gen-115agwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-49" bind-source="screenshot1"></gwd-image>
      <gwd-image class="gwd-img-1j97 gwd-grp-834h gwd-gen-crl4gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-50" bind-source="screenshot2"></gwd-image>
      <div class="gwd-animation-event event-3-animation" data-event-name="event-3" data-event-time="0.01"></div>
      <div class="gwd-animation-event event-4-animation" data-event-name="event-4" data-event-time="2300"></div>
      <div class="gwd-animation-event event-5-animation" data-event-name="event-5" data-event-time="1000"></div>
    </div>
    <div data-gwd-group-def="animation-group-l" data-gwd-group-class="gwd-grp-9fox" style="display: none;">
      <gwd-image class="gwd-img-s9v4 gwd-grp-9fox gwd-gen-1ba7gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-75" bind-source="screenshot1"></gwd-image>
      <gwd-image class="gwd-img-6xd3 gwd-grp-9fox gwd-gen-1psmgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-74" bind-source="screenshot2"></gwd-image>
      <gwd-image class="gwd-img-186s gwd-grp-9fox gwd-gen-19sjgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-73" bind-source="screenshot3"></gwd-image>
      <gwd-image class="gwd-img-v8gd gwd-grp-9fox gwd-gen-1491gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-72" bind-source="screenshot4"></gwd-image>
      <gwd-image class="gwd-img-1dtr gwd-grp-9fox gwd-gen-d63ngwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-71" bind-source="screenshot1"></gwd-image>
      <gwd-image class="gwd-img-ue35 gwd-grp-9fox gwd-gen-1ss7gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-70" bind-source="screenshot2"></gwd-image>
      <gwd-image class="gwd-img-130p gwd-grp-9fox gwd-gen-tga0gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-69" bind-source="screenshot3"></gwd-image>
      <gwd-image class="gwd-img-1r5v gwd-grp-9fox gwd-gen-1x2lgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-68" bind-source="screenshot4"></gwd-image>
      <gwd-image class="gwd-img-x8sf gwd-grp-9fox gwd-gen-b2w9gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-67" bind-source="screenshot1"></gwd-image>
      <gwd-image class="gwd-img-g4yb gwd-grp-9fox gwd-gen-1ob8gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-66" bind-source="screenshot2"></gwd-image>
      <gwd-image class="gwd-img-1er1 gwd-grp-9fox gwd-gen-a805gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-65" bind-source="screenshot3"></gwd-image>
      <gwd-image class="gwd-img-1o10 gwd-grp-9fox gwd-gen-7glzgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-64" bind-source="screenshot4"></gwd-image>
      <gwd-image class="gwd-img-iwso gwd-grp-9fox gwd-gen-1g66gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-63" bind-source="screenshot1"></gwd-image>
      <gwd-image class="gwd-img-v6qm gwd-grp-9fox gwd-gen-iurygwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-62" bind-source="screenshot2"></gwd-image>
      <gwd-image class="gwd-img-1z0y gwd-grp-9fox gwd-gen-k64agwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-61" bind-source="screenshot3"></gwd-image>
      <gwd-image class="gwd-img-1q5u gwd-grp-9fox gwd-gen-1gcpgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-60" bind-source="screenshot4"></gwd-image>
      <gwd-image class="gwd-img-la9n gwd-grp-9fox gwd-gen-1wn3gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-59" bind-source="screenshot1"></gwd-image>
      <gwd-image class="gwd-img-1sk3 gwd-grp-9fox gwd-gen-evc7gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-58" bind-source="screenshot2"></gwd-image>
      <gwd-image class="gwd-img-cau2 gwd-grp-9fox gwd-gen-1x8cgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-57" bind-source="screenshot3"></gwd-image>
      <gwd-image class="gwd-img-1ot9 gwd-grp-9fox gwd-gen-1ankgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-56" bind-source="screenshot4"></gwd-image>
      <gwd-image class="gwd-img-vhcg gwd-grp-9fox gwd-gen-144rgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-55" bind-source="screenshot1"></gwd-image>
      <gwd-image class="gwd-img-1aax gwd-grp-9fox gwd-gen-148tgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-54" bind-source="screenshot2"></gwd-image>
      <gwd-image class="gwd-img-111z gwd-grp-9fox gwd-gen-19jzgwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-53" bind-source="screenshot3"></gwd-image>
      <gwd-image class="gwd-img-33ec gwd-grp-9fox gwd-gen-w7sigwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-52" bind-source="screenshot4"></gwd-image>
      <gwd-image class="gwd-img-145y gwd-grp-9fox gwd-gen-1ee1gwdanimation" source="assets/img.svg" scaling="cover" data-gwd-grp-id="img-51" bind-source="screenshot1"></gwd-image>
      <div class="gwd-animation-event event-1-animation" data-event-name="event-1" data-event-time="0.01"></div>
      <div class="gwd-animation-event event-2-animation" data-event-name="event-2" data-event-time="2400"></div>
    </div>
  </template>
  <gwd-gpa-data-provider id="gpa-data-provider" gwd-schema-id="app_promo_install" network-schema-id="442"></gwd-gpa-data-provider>
  <gwd-data-binder id="gwd-data-binder_1"></gwd-data-binder>
  <gwd-text-helper id="gwd-text-helper_1" preserve-text-style-for-selector="[bind-text],[bind-html]" fit-font-size-for-selector="[data-gwd-fit-font-size],[gwd-fitting-truncate]" data-gwd-fit-font-size="false"></gwd-text-helper>
  <gwd-google-ad id="gwd-ad" polite-load="" data-provider="gpa-data-provider">
    <gwd-metric-configuration>
      <gwd-metric-event source="gallery-l" event="firstinteraction" metric="gallery-l: Gallery Swiped"></gwd-metric-event>
      <gwd-metric-event source="gallery-l" event="allframesviewed" metric="gallery-l: All Frames Viewed"></gwd-metric-event>
      <gwd-metric-event source="gallery-p" event="firstinteraction" metric="gallery-p: Gallery Swiped"></gwd-metric-event>
      <gwd-metric-event source="gallery-p" event="allframesviewed" metric="gallery-p: All Frames Viewed"></gwd-metric-event>
      <gwd-metric-event source="DELETE-desktop-test-taparea-p" event="tapareaexit" metric="" exit="Exit"></gwd-metric-event>
      <gwd-metric-event source="DELETE-desktop-test-taparea-l" event="tapareaexit" metric="" exit="Exit"></gwd-metric-event>
      <gwd-metric-event source="gallery-l" event="frameexit" metric="" exit="Gallery Frame Exited"></gwd-metric-event>
      <gwd-metric-event source="cta-l" event="tapareaexit" metric="" exit="Exit"></gwd-metric-event>
      <gwd-metric-event source="gallery-p" event="frameexit" metric="" exit="Gallery Frame Exited"></gwd-metric-event>
      <gwd-metric-event source="cta-p" event="tapareaexit" metric="" exit="Exit"></gwd-metric-event>
    </gwd-metric-configuration>
    <gwd-pagedeck class="gwd-page-container" id="pagedeck" data-gwd-offset-top="0px" data-gwd-offset-left="0px">
      <gwd-page id="page1" class="gwd-page-wrapper gwd-page-size gwd-lightbox gwd-div-1118" data-gwd-width="320px" data-gwd-height="480px" data-gwd-name="intro-portrait" alt-orientation-page="page1_1" centered="">
        <div class="gwd-page-content gwd-page-size gwd-div-13rh">
          <gwd-image class="gwd-img-1oxl" id="bg-img-p" source="assets/bg.gif" data-gwd-tl-hidden=""></gwd-image>
          <div class="gwd-div-6mbx" data-gwd-group="animation-group-p" id="animation-group-p"></div>
          <div class="gwd-div-yjjv" id="shake-overlay-p" data-gwd-tl-hidden=""></div>
          <div class="gwd-div-13xq" id="shake-cta-p" data-gwd-tl-hidden="">Shake to Reveal</div>
          <gwd-taparea id="DELETE-desktop-test-taparea-p" class="gwd-taparea-13k2" data-gwd-tl-hidden=""></gwd-taparea>
        </div>
      </gwd-page>
      <gwd-page id="page1_1" class="gwd-page-wrapper gwd-page-size gwd-lightbox gwd-div-14y6" data-gwd-width="480px" data-gwd-height="320px" data-gwd-name="intro-landscape" alt-orientation-page="page1" centered="">
        <div class="gwd-page-content gwd-page-size gwd-div-1pzo">
          <gwd-image class="gwd-img-43t3" id="bg-img-l" source="assets/bg.gif" data-gwd-tl-locked=""></gwd-image>
          <div class="gwd-div-rxwe" data-gwd-group="animation-group-l" id="animation-group-l"></div>
          <div class="gwd-div-eo6l" id="shake-overlay-l" data-gwd-tl-locked=""></div>
          <div class="gwd-div-cyj4" id="shake-cta-l" data-gwd-tl-locked="">Shake to Reveal</div>
          <gwd-taparea id="DELETE-desktop-test-taparea-l" class="gwd-taparea-1cwh" data-gwd-tl-locked=""></gwd-taparea>
        </div>
      </gwd-page>
      <gwd-page id="page1_2" class="gwd-page-wrapper gwd-lightbox gwd-div-9q9e" data-gwd-width="480px" data-gwd-height="320px" data-gwd-name="app-promo-landscape" alt-orientation-page="page1_3" centered="">
        <div class="gwd-page-content gwd-div-1ua0">
          <gwd-image class="gwd-img-12kx" id="app-bg-img-l" source="assets/bg.gif"></gwd-image>
          <gwd-carouselgallery id="gallery-l" scaling="contain" class="gwd-carouselgallery-1lw8" bind-images="screenshots | join ," frame-width="480" frame-height="160" neighbor-rotation-y="38" neighbor-translation-x="325" neighbor-translation-y="-8" neighbor-translation-z="-80" images="assets/img-l.png,assets/img-l.png,assets/img-l.png,assets/img-l.png" clamp-frame-size-to-image="false"></gwd-carouselgallery>
          <div class="gwd-div-1ag3" id="nav-group-l">
            <div class="gwd-div-1k8j" id="nav-bg-l"></div>
            <gwd-gallerynavigation id="gal-nav-l" class="gwd-gallerynavigation-11t7" for="gallery-l" bind-images="screenshots | join ,"></gwd-gallerynavigation>
          </div>
          <div class="gwd-div-mjvo" id="reviews-l">(<span class="gwd-span-rev1" bind-text="reviews" data-gwd-fit-font-size="">12345</span>)</div>
          <gwd-starratings id="stars-l" ratingvalue="4" isemptyshown="" isemptycolored="" class="gwd-starratings-g5xd" colorprimary="#f3b500" colorsecondary="#f3b500" iconsize="18" bind-ratingvalue="rating"></gwd-starratings>
          <div class="gwd-div-136e" id="desc-txt-l" bind-text="promoDescription" style="font-size: 13px;" data-gwd-fit-font-size="">Description Text Description Text Description</div>
          <div class="gwd-div-2hgu" id="headline-txt-l" bind-text="promoHeadline" data-gwd-fit-font-size="">Headline Text</div>
          <div class="gwd-div-1prl" id="appname-l" bind-text="appName" data-gwd-fit-font-size="">App Name</div>
          <gwd-image class="gwd-img-a027" id="appicon-l" source="assets/icon.png" bind-source="appIcon"></gwd-image>
          <gwd-taparea id="cta-l" class="gwd-taparea-m3xh">
            <gwd-image class="gwd-img-6udd" id="cta-bg-l" source="assets/button.png"></gwd-image>
            <div class="gwd-div-x2lz" id="cta-txt-l" bind-text="callToAction" data-gwd-fit-font-size="">INSTALL</div>
          </gwd-taparea>
        </div>
      </gwd-page>
      <gwd-page id="page1_3" class="gwd-page-wrapper gwd-lightbox gwd-div-1kn6" data-gwd-width="320px" data-gwd-height="480px" data-gwd-name="app-promo-portrait" alt-orientation-page="page1_2" centered="">
        <div class="gwd-page-content gwd-div-1cau">
          <gwd-image class="gwd-img-3a63" id="app-bg-img-p" source="assets/bg.gif"></gwd-image>
          <gwd-carouselgallery id="gallery-p" scaling="contain" class="gwd-carouselgallery-70vd" bind-images="screenshots | join ," frame-width="260" frame-height="190" neighbor-rotation-y="45" neighbor-translation-x="80" neighbor-translation-y="-8" neighbor-translation-z="-80" images="assets/img-l.png,assets/img-l.png,assets/img-l.png,assets/img-l.png" clamp-frame-size-to-image="false"></gwd-carouselgallery>
          <div class="gwd-div-gpa7" id="nav-group-p">
            <div class="gwd-div-9n3c" id="nav-bg-p"></div>
            <gwd-gallerynavigation id="gal-nav-p" class="gwd-gallerynavigation-1xi0" for="gallery-p"></gwd-gallerynavigation>
          </div>
          <div class="gwd-div-1dn9" id="reviews-p">(<span class="gwd-span-rev2" bind-text="reviews" data-gwd-fit-font-size="">12345</span>)</div>
          <gwd-starratings id="stars-p" ratingvalue="4" isemptyshown="" isemptycolored="" class="gwd-starratings-1m7u" colorprimary="#f3b500" colorsecondary="#f3b500" iconsize="18" bind-ratingvalue="rating"></gwd-starratings>
          <div class="gwd-div-kvkc" id="desc-txt-p" bind-text="promoDescription" style="font-size: 13px;" data-gwd-fit-font-size="">Description Text&nbsp;Description Text&nbsp;Description Text&nbsp;Description Text</div>
          <div class="gwd-div-1qh9" id="headline-txt-p" bind-text="promoHeadline" data-gwd-fit-font-size="">Headline Text</div>
          <div class="gwd-div-1pjh" id="appname-p" bind-text="appName" data-gwd-fit-font-size="">App Name</div>
          <gwd-image class="gwd-img-1pqe" id="appicon-p" source="assets/icon.png" bind-source="appIcon"></gwd-image>
          <gwd-taparea id="cta-p" class="gwd-taparea-4q4d">
            <gwd-image class="gwd-img-17hz" id="cta-bg-p" source="assets/button.png"></gwd-image>
            <div class="gwd-div-2vxp" id="cta-txt-p" bind-text="callToAction" data-gwd-fit-font-size="">
              INSTALL
            </div>
          </gwd-taparea>
        </div>
      </gwd-page>
    </gwd-pagedeck>
    <gwd-exit metric="Exit-L" url=""></gwd-exit>
    <gwd-exit metric="Exit-P" url=""></gwd-exit>
  </gwd-google-ad>
  <script id="gwd-init-code">
    (function() {
      var gwdAd = document.getElementById('gwd-ad');
      /**
       * Handles the DOMContentLoaded event. The DOMContentLoaded event is
       * fired when the document has been completely loaded and parsed.
       */

      function handleDomContentLoaded(event) {
        // This is a good place to show a loading or branding image while
        // the ad loads.
      }

      /**
       * Handles the WebComponentsReady event. This event is fired when all
       * custom elements have been registered and upgraded.
       */
      function handleWebComponentsReady(event) {
        // Start the Ad lifecycle.
        requestAnimationFrame(function() {
          setTimeout(function() {
            gwdAd.initAd();
          }, 1);
        });
      }

      /**
       * Handles the event that is dispatched after the Ad has been
       * initialized and before the default page of the Ad is shown.
       */
      function handleAdInitialized(event) {
        // This marks the end of the polite load phase of the Ad. If a
        // loading image was shown to the user, this is a good place to
        // remove it.
      }

      window.addEventListener('DOMContentLoaded',
        handleDomContentLoaded, false);
      window.addEventListener('WebComponentsReady',
        handleWebComponentsReady, false);
      window.addEventListener('adinitialized',
        handleAdInitialized, false);
    })();
  </script>
</body>

</html>

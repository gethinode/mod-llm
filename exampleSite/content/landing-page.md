---
_schema: default
title: Become a digital leader
description: A business landing page theme for your Hugo site based on Bootstrap 5.
content_blocks:
  - _bookshop_name: hero
    heading:
      title: Become a **digital leader**
      content: >-
        Grow your business by delivering a next-level customer experience. From
        ideation to realization, we help you to digitally transform your business.
      align: start
      size: 1
      width: 6
    illustration:
      image: /static/img/logo-dark.svg
      width: 10
    links:
      - title: Get in touch
        url: '#!'
        icon: chevron-right
    orientation: horizontal
    fluid: true
    cover: true

  - _bookshop_name: testimonials
    cols: 5
    background:
      color: body-tertiary
    icon_style: fa-2xl text-secondary
    align: center
    responsive: false
    testimonials:
      - icon: fab github
      - icon: fab node
      - icon: fab unsplash
      - icon: fab font-awesome
      - icon: fab sass

  - _bookshop_name: cards
    heading:
      preheading: Our values
      title: Data-driven value creation with a human touch
    cols: 3
    padding: 0
    elements:
      - title: People oriented
        icon: person-arms-up
        content: >-
          People are at the heart of any organization. We take a people-centric
          approach to your digital transformation.
      - title: Value obsessed
        icon: heart
        content: We ensure your digital investments bring tangible business value.
      - title: Tech savvy
        icon: cpu
        content: >-
          Technology advances at an incredible pace. We help you identify and
          utilize the right technology.

  - _bookshop_name: about
    heading:
      preheading: What we are
      title: Experts in digitalization
      content: >-
        We help organizations to become digital leaders in their industry. We
        have a proven track record with more than 50% of the organizations in
        the Fortune 500. Get in touch to find out how we can help you.
      align: start
    width: 8
    illustration:
      image: /assets/img/pexels-motional-studio-1081685.jpg
    links:
      - title: Get in touch
        url: '#!'
        icon: chevron-right
    order: first
    background:
      color: primary
      subtle: true

  - _bookshop_name: cards
    heading:
      preheading: Our services
      title: From ideation to realization
      content: >-
        We provide a full range of services to help you digitally transform your
        business.
      align: start
    background:
      color: body-tertiary
    orientation: horizontal
    padding: 0
    elements:
      - title: Strategy & Transformation
        icon: star-fill
        content: >-
          We help you shape and realize a compelling and tangible digital
          strategy based on business outcomes.
        link: /en/services/strategy-transformation/
      - title: Experience Design
        icon: hand-thumbs-up-fill
        content: >-
          We digitize your processes, products, and services to realize a
          next-level customer experience.
        link: /en/services/experience-design/
      - title: Platform Engineering
        icon: stack
        content: >-
          We design and implement a modern technology stack that scales with
          your business.
        link: /en/services/platform-engineering/

  - _bookshop_name: articles
    heading:
      preheading: Blog
      title: Recent posts
      align: start
    hide_empty: false
    header_style: none
    input:
      section: blog
      reverse: true
      sort: date
    more:
      title: More blog posts
    cols: 3
    padding: 0
    limit: 3
---

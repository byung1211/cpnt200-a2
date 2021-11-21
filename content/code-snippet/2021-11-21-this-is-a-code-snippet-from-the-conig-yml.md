---
title: This is a code snippet from the conig.yml.
date: 2021-11-21T02:55:21.643Z
code:
  code: |-2
      - name: 'code-snippet'
        label: 'Code snippet'
        folder: 'content/code-snippet'
        format: 'frontmatter'
        create: true
        slug: '{{year}}-{{month}}-{{day}}-{{slug}}'
        editor:
          preview: false
        fields:
          - { label: 'Title', name: 'title', widget: 'string' }
          - { label: 'Date', name: 'date', widget: 'datetime' }
          - { label: 'Code', name: 'code', widget: 'code' }
          - { label: 'Description', name: 'description', widget: 'markdown' }
description: Code Snippet collection configuration in the yml file.
---

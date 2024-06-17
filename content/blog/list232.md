---
title: '[자료구조] 단순 연결 리스트 '
status: 'draft'
slug: 'list232'
description: ''
coverImage: ''
tags: []
publishedAt: '2024-06-17T01:55:09.591Z'
---
## 단순 연결 리스트
 - 노드마다 하나의 포인터 영역을 가지며, 이전 노드의 포인터가 다음 노드를
   가리키면서 서로 연결된 구조 
 - 헤드 포인터(head pointer)가 첫 번째 노드와 연결
 - 한 개의 노드는 실제 자료를 저장하는 데이터 영역과 다음 자료가 저장된 노드를
   가리키는 포인터 영역(next)로 구성됨
 - 포인터를 통하여 연결되어 있는 각 자료에 접근할 수 있음
 - 마지막 노드는 더 이상 연결할 후속 노드가 없으므로 next를 null로 설정 
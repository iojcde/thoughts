---
title: '[자료구조] 이중 연결 리스트'
status: 'draft'
slug: 'dll'
description: ''
coverImage: ''
tags: []
publishedAt: '2024-06-24T01:55:09.591Z'
---

# 이중연결리스트(doublely linked list)
단일 연결리스트가 확장되어 Node들을 단방향이아닌 양방향으로 연결시킬 수 있도록 하여 이전, 다음 Node들을 모두 추적할 수 있도록 만든 자료구조

### 1. 자료삽입

새로운 노드를 생성하고, 데이터 영역에 새로운 자료(예: 나)를 저장하기.
새로운 노드의 왼쪽 포인터와 오른쪽 포인터는 아직 연결되지 않은 상태

새로운 노드(나)의 오른쪽 포인터가 삽입 위치의 다음 노드(다)를 가리키도록 설정하기.
새로운 노드(나)의 왼쪽 포인터는 삽입 위치의 이전 노드(가)를 가리키도록 설정하기.

후속 노드(다)의 왼쪽 포인터는 새로운 노드(나)를 가리키도록 업데이트.
선행 노드(가)의 오른쪽 포인터 역시 새로운 노드(나)를 가리키도록 업데이트

맨 앞 삽입
```
void insert_front_dnode(int data) {
	// 삽입할 새로운 node 선언
    Dnode* newNode = (Dnode*)malloc(sizeof(Dnode));
    newNode -> value = data;
    newNode -> prev = NULL;
    newNode -> next = NULL;
    
    if (head == NULL) {		// 리스트가 비어있다면
    	head = newNOde;
        tail = newNode;
        return;
	}
    
    // newNode의 next가 head를 가리키는 노드를 가리킬 수 있도록 함
    newNode -> next = head;
    
    // head가 가리키는 노드의 이전 포인터가 newNode를 가리키도록 함
    head -> prev = newNode;
    
    // head가 newNode를 가리킬 수 있도록 함
    head = newNode;
}
```

맨 뒤 삽입
```
void insert_rear_dnode(int data) {
	// 삽입할 새로운 node 선언
    Dnode* newNode = (Dnode*)malloc(sizeof(Dnode));
    newNode -> value = data;
    newNode -> prev = NULL;
    newNode -> next = NULL;
    
    if (head == NULL) {		// 리스트가 비어있다면
    	head = newNOde;
        tail = newNode;
        return;
	}
    
    // newNode의 prev가 tail이 가리키는 노드를 가리킬 수 있도록 함
    newNode -> prev = tail;
    
    // tail이 가리키는 이전 노드가 다음 노드로 newNode를 가리키도록 함
    tail -> next = newNode;
    
    // tail이 newNode를 가리키도록 함
    tail = newNode;
}
```

삭제하고자 하는 노드(나)의 이전 노드(가)의 오른쪽 포인터가 다음 노드(다)를 가리키게 하기
삭제하고자 하는 노드(나)의 다음 노드(다)의 왼쪽 포인터가 이전 노드(가)를 가리키게 하기
 
맨 앞 삭제

```
void remove_front_dnode() {
	Dnode* delNode;			// 삭제할 노드를 저장할 노드 선언
    
    if (head == NULL) {		// 리스트가 비어있는 경우
    	return;
    }
    
    delNode = head;			// 삭제할 node를 delNode에 저장
    // 헤드가 가리키는 노드의 다음 노드를 가리키도록 설정
    head = head -> next;
    free(delNode);			// 삭제된 node의 메모리 제거
    
    if(head)				// head가 존재 한다면
    	head -> prev = NULL;// head의 이전 포인터를 NULL
    
    if(!head)				// head가 존재하지 않는다면
    	tail = NULL;		// list가 없다는 것으로 tail도 NULL
}


맨 뒤 삭제 
```
void remove_rear_dnode() {
	Dnode* delNode;			// 삭제할 노드를 저장할 노드 선언
    
    if (head == NULL) {		// 리스트가 비어있는 경우
    	return;
    }
    
    delNode = tail;			// 삭제할 node를 delNode에 저장
    // tail이 가리키는 노드가 이전 노드를 가리키도록 함
    tail = tail -> prev;
    free(delNode);			// 삭제된 node의 메모리 제거
    
    if(tail)				// tail이 존재 한다면
    	tail -> next = NULL;// tail의 다음 포인터를 NULL
	
    if(!tail)				// tail이 존재하지 않는다면
    	head = NULL;		// list에 값이 없다는 것으로 head도 NULL
}
``` 

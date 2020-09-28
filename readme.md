# @bytesoftio/use-list

## Installation

`yarn add @bytesoftio/use-list` or `npm install @bytesoftio/use-list`

## Table of contents

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [Description](#description)
  - [useList](#uselist)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Description

This package provides a React integration for [@bytesoftio/list](https://github.com/bytesoftio/list).

### useList

Use this helper to hook up a store inside a React component.

```tsx
import React from "react"
import {createList} from "@bytesoftio/list"
import {useList} from "@bytesoftio/use-list"

const globalList = createList(["apple", "oranges"])

const Component = () => {
  // create a new list
  const list1 = useList(["apples"])

  // create a new list through an initializer / factory function
  const list2 = useList(globalList) 
  
  const addItem = () => list1.add("oranges")
  const addItemGlobal = () => list2.add("tomatos")
 
  return (
    <div>
      <button onClick={addItem}>local items: {list1.get().join(",")}</button>    
      <button onClick={addItemGlobal}>global items: {globalList.get().join(",")}</button>    
    </div>
  )
} 
```

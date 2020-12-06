---
layout: articles 
title:  "Selection Sort"
date:   2020-12-05 23:44:52 +0800
categories: jekyll update
---

- This blog is used as notes for later reference after reading the book 'Algorithms an illustrated guide for programmers'

## Chapter 2: Selection Sort

### 1. Tips About Selection Sort
* Your computer’s memory is like a giant set of drawers.
* When you want to store multiple elements, use an array or a list.
* With an array, all your elements are stored right next to each other.
* With a list, elements are strewn all over, and one element stores the address of the next one.
* Arrays allow fast reads.
* Linked lists allow fast inserts and deletes.
* All elements in the array should be the same type (all ints, all doubles, and so on).

### 2. Codes in about Selection Sort
* Python
{% highlight ruby %}
def findSmallest(arr):
    smallest = arr[0]
    smallest_idx = 0 
    for i in range(1, len(arr)):
        if arr[i] < smallest:
            smallest = arr[i]
            smallest_idx = i 
    return smallest_idx 

def selectionSort(arr):
    newArr = [] 
    for i in range(len(arr)):
        smallest = findSmallest(arr) 
        newArr.append(arr.pop(smallest)) 
    return newArr 

print selectionSort([5, 3, 6, 2, 10])
{% endhighlight %}

- Golang 
{% highlight ruby %}
package main

import "fmt"

func findSmallest(arr []int) int {
	smallest := arr[0]
	smallest_idx := 0
	for idx, val := range arr {
		if val < smallest {
			smallest = val
			smallest_idx = idx
		}
	}
	return smallest_idx
}

func SelectionSort(arr []int) (ret []int) {
	l := len(arr)
	for i := 0; i < l; i++ {
		fmt.Println("arr: ", arr)
		smallest_idx := findSmallest(arr)
		ret = append(ret, arr[smallest_idx])
		arr = append(arr[:smallest_idx], arr[smallest_idx+1:]...)
	}
	return
}

func main() {
	arr := []int{5, 3, 6, 2, 10}
	fmt.Println(SelectionSort(arr))
}

{% endhighlight %}





Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/

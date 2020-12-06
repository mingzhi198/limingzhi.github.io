---
layout: article 
categories: algorithm_illustration 
title:  "Binary Search"
date:   2020-12-05 23:44:52 +0800
---
[//]: * 目录
[//]: {:toc}

- This blog is used as notes for later reference after reading the book 'Algorithms an illustrated guide for programmers'

## Chapter 1: Binary Search

### 1. Tips About Binary Search
	* Binary search is a lot faster than simple search.
	* O(log n) is faster than O(n), but it gets a lot faster once the list of items you’re searching through grows.
	* Algorithm speed isn’t measured in seconds.
	* Algorithm times are measured in terms of growth of an algorithm.
	* Algorithm times are written in Big O notation.

### 2. Codes in about Binary Search
* Python
{% highlight ruby %}
def binary_search(list, item):
    low = 0
    high = len(list)-1

    while low <= high:
        mid = (low + high)/2 
        guess = list[mid]
        if guess == item:
            return mid 
        if guess > item: 
            high = mid -1 
        else: 
            low = mid + 1
    return None 


my_list = [1, 3, 5, 7, 9]
print binary_search(my_list, 5) 
print binary_search(my_list, -1)
{% endhighlight %}

- Golang 
{% highlight ruby %}
func BinarySearch(list []int, item int) int {
	low := 0
	high := len(list) - 1

	for low <= high {
		mid := (low + high) / 2
		guess := list[mid]
		if guess == item {
			return mid
		}
		if guess > item {
			high = mid - 1
		} else {
			low = mid + 1
		}
	}
	return -1
}

func main() {
	my_list := []int{1, 3, 5, 7, 9}
	fmt.Println(BinarySearch(my_list, 5))
	fmt.Println(BinarySearch(my_list, -1))
}

{% endhighlight %}




#### Five Big O run times sorted from fastest to slowest:
```
* O(log n), also known as log time. Example: Binary search.
* O(n), also known as linear time. Example: Simple search.
* O(n * log n). Example: A fast sorting algorithm, like quicksort.
* O(n2). Example: A slow sorting algorithm, like selection sort.  
* O(n!). Example: A really slow algorithm, like the traveling salesperson.
```



Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/

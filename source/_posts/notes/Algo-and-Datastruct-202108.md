---
title: 數據結構與算法部分題目Ⅰ幾個簡單的排序
mathjax: true
date: 2021-08-31 18:38:58
tags:
- Notes(代码笔记)
---

```cpp headers
#include <cstdio>
#include <cstdlib>
#include <cstring>
#include <iostream>

using namespace std;
using namespace __gnu_cxx;
```

```cpp q2085
int m, cur_val;
int min_val = 2147483647;
int max_inc = -1;

int main(int argc, char *argv[]) {
    scanf("%d", &m);
    for (int idx = 0; idx < m; ++idx) {
        scanf("%d", &cur_val);
        max_inc = max(cur_val - min_val, max_inc);
        min_val = min(cur_val, min_val);
    }
    printf("%d\n", max_inc);
    return 0;
}
```

```cpp q1075
int m, val[101], cnt_swap = 0;

void bubblesort(int *arr, int arlength) {
    if (arlength) {
        for (int idx = 0; idx < arlength - 1; ++idx) {
            if (arr[idx] > arr[idx + 1]) {
                swap(arr[idx], arr[idx + 1]);
                ++cnt_swap;
            }
        }
        return bubblesort(arr, arlength - 1);
    }
}

int main(int argc, char *argv[]) {
    scanf("%d", &m);
    for (int idx = 0; idx < m; ++idx)
        scanf("%d", &val[idx]);
    bubblesort(val, m);
    for (int idx = 0; idx < m; ++idx)
        printf("%d ", val[idx]);
    printf("\n%d\n", cnt_swap);
    return 0;
}
```

```cpp q1076
int m, val[101], cnt_swap = 0;

void selectsort(int *arr, int starter) {
    if ((m - 1) - starter) {
        int idx_min = starter;
        for (int idx = starter; idx < m; ++idx)
            idx_min = (arr[idx] < arr[idx_min]) ? idx : idx_min;
        if (starter < idx_min) {
            swap(arr[starter], arr[idx_min]);
            ++cnt_swap;
        }
        return selectsort(arr, starter + 1);
    }
}

int main(int argc, char *argv[]) {
    scanf("%d", &m);
    for (int idx = 0; idx < m; ++idx)
        scanf("%d", &val[idx]);
    selectsort(val, 0);
    for (int idx = 0; idx < m; ++idx)
        printf("%d ", val[idx]);
    printf("\n%d\n", cnt_swap);
    return 0;
}
```

```cpp q1077
int m, val[101], cnt_swap = 0;

int main(int argc, char *argv[]) {
    scanf("%d", &m);
    for (int idx = 0; idx < m; ++idx)
        scanf("%d", &val[idx]);
    for (int k = 1; k < m; ++k) {
        for (int idx = 0; idx < m; ++idx)
            printf("%d ", val[idx]);
        putchar('\n');
        for (int l = k; l > 0; --l)
            if (val[l] < val[l - 1]) {
                swap(val[l], val[l - 1]);
                ++cnt_swap;
            }
    }
    for (int idx = 0; idx < m; ++idx)
        printf("%d ", val[idx]);
    putchar('\n');
    return 0;
}
```

```cpp q1078
int m, val, buckets[10001];

int main(int argc, char *argv[]) {
    scanf("%d", &m);
    for (int idx = 0; idx < m; ++idx) {
        scanf("%d", &val);
        ++buckets[val];
    }
    for (int k = 0; k <=10000; ++k)
        for (int l = 0; l < buckets[k]; ++l)
            printf("%d ", k);
    return 0;
}
```
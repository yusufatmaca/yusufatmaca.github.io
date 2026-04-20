---
title: "std::atomic ve memory ordering notları"
date: 2026-04-20
tags: [c++, concurrency]
---

Paralel kodda `std::memory_order_relaxed` kullanımı...

```cpp
#include 
#include 

std::atomic counter{0};

void worker() {
    for (int i = 0; i < 1000; ++i) {
        counter.fetch_add(1, std::memory_order_relaxed);
    }
}
```

Sonraki kısım...

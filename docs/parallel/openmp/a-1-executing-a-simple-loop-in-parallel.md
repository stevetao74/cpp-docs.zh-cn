---
title: A.1   并行执行简单循环
ms.date: 11/04/2016
ms.assetid: b8aaacae-b20d-4b16-a540-54ccbf09582b
ms.openlocfilehash: 5bd9a9c8b1d226c67f7e9031a547e551fae3407b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558933"
---
# <a name="a1---executing-a-simple-loop-in-parallel"></a>A.1   并行执行简单循环

下面的示例演示如何以并行执行简单的循环使用`parallel for`指令 ([部分 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md)第 16 页上)。 循环迭代变量是默认情况下，专用的因此不需要专用的子句中显式指定它。

```
#pragma omp parallel for
    for (i=1; i<n; i++)
        b[i] = (a[i] + a[i-1]) / 2.0;
```
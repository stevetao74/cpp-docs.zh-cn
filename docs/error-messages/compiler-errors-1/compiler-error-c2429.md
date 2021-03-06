---
title: 编译器错误 C2429
ms.date: 11/16/2017
f1_keywords:
- C2429
helpviewer_keywords:
- C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
ms.openlocfilehash: 972ec6591132443ef4d1297598d6de7216f59663
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50586688"
---
# <a name="compiler-error-c2429"></a>编译器错误 C2429

> '*语言功能*需要编译器标志'*编译器选项*

语言功能需要支持特定的编译器选项。

错误**C2429： 语言功能嵌套的命名空间的定义需要编译器标志 / /std: c + + 17'** 如果你尝试定义生成*复合命名空间*，一个包含一个或多个命名空间启动 Visual Studio 2015 Update 5 中的作用域嵌套命名空间名称。 (在 Visual Studio 2017 版本 15.3 中， **/std: c + + 最新**交换机是必需的。)复合命名空间定义中不允许使用 c + + 在 C + + 17 之前。 编译器支持复合命名空间定义时[/std: c + + 17](../../build/reference/std-specify-language-standard-version.md)指定编译器选项：

```cpp
// C2429a.cpp
namespace a::b { int i; } // C2429 starting in Visual C++ 2015 Update 3.
                          // Use /std:c++17 to fix, or do this:
// namespace a { namespace b { int i; }}

int main() {
   a::b::i = 2;
}
```

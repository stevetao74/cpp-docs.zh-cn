---
title: 编译器错误 C3062
ms.date: 11/04/2016
f1_keywords:
- C3062
helpviewer_keywords:
- C3062
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
ms.openlocfilehash: ac45847c94e7d2dc731eba71b0a38105eb915e53
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50590406"
---
# <a name="compiler-error-c3062"></a>编译器错误 C3062

enum： 枚举数需要值，因为基础类型为 type

可以指定一个枚举的基础类型。 但是，某些类型需要您要将值分配到每个枚举器。

枚举的详细信息，请参阅[枚举类](../../windows/enum-class-cpp-component-extensions.md)。

下面的示例生成 C3062:

```
// C3062.cpp
// compile with: /clr

enum class MyEnum : bool { a };   // C3062
enum class MyEnum2 : bool { a = true};   // OK
```
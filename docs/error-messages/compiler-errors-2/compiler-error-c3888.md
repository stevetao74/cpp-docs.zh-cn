---
title: 编译器错误 C3888
ms.date: 11/04/2016
f1_keywords:
- C3888
helpviewer_keywords:
- C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
ms.openlocfilehash: 067412e59041cb98b68cb373c4671c243ab8a0ec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479061"
---
# <a name="compiler-error-c3888"></a>编译器错误 C3888

“name”：C++/CLI 不支持与此 literal 数据成员关联的常量表达式

使用 *literal* 关键字声明的 [名称](../../windows/literal-cpp-component-extensions.md) 数据成员是使用编译器不支持的值初始化的。 编译器仅支持常量整型、枚举或字符串类型。 **C3888** 错误可能的原因是数据成员是使用字节数组初始化的。

### <a name="to-correct-this-error"></a>更正此错误

1. 检查声明的 literal 数据成员是否是支持的类型。

## <a name="see-also"></a>请参阅

[名称](../../windows/literal-cpp-component-extensions.md)
---
title: 编译器错误 C3180
ms.date: 11/04/2016
f1_keywords:
- C3180
helpviewer_keywords:
- C3180
ms.assetid: 5281f583-7df7-418a-8507-d4da67ed6572
ms.openlocfilehash: bfe2699ce448aa879f0c93aa431a17dbc1334274
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662028"
---
# <a name="compiler-error-c3180"></a>编译器错误 C3180

type name： 名称超出了 limit 个字符的元数据限制

编译器截断元数据中的托管类型的名称。 截断将使类型无法通过`#using`指令 （或另一种语言的等效项）。

类型名称限制包括任何命名空间限定。
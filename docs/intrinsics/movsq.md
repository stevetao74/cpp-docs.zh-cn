---
title: __movsq
ms.date: 11/04/2016
f1_keywords:
- __movsq
helpviewer_keywords:
- __movsq intrinsic
- rep movsq instruction
- movsq instruction
ms.assetid: be116a6e-2176-4ca4-93b1-9ccf3e7e7835
ms.openlocfilehash: 06f42befa24d4024b3ad4b0c0a8d0897cb2aee9b
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326363"
---
# <a name="movsq"></a>__movsq

**Microsoft 专用**

生成重复移动字符串 (`rep movsq`) 指令。

## <a name="syntax"></a>语法

```
void __movsq(
   unsigned char* Dest,
   unsigned char* Source,
   size_t Count
);
```

#### <a name="parameters"></a>参数

*dest*<br/>
[out]该操作的目标。

*源*<br/>
[in]操作的源。

“计数”<br/>
[in]要复制的四字的数目。

## <a name="requirements"></a>要求

|内部函数|体系结构|
|---------------|------------------|
|`__movsq`|X64|

**标头文件** \<intrin.h >

## <a name="remarks"></a>备注

结果是，第一个`Count`指向四字`Source`复制到`Dest`字符串。

此例程仅可用作内部函数。

## <a name="example"></a>示例

```
// movsq.cpp
// processor: x64
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(__movsq)

int main()
{
    unsigned __int64 a1[10];
    unsigned __int64 a2[10] = {950, 850, 750, 650, 550, 450, 350, 250,
                               150, 50};
    __movsq(a1, a2, 10);

    for (int i = 0; i < 10; i++)
       printf_s("%d ", a1[i]);
    printf_s("\n");
}
```

```Output
950 850 750 650 550 450 350 250 150 50
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[编译器内部函数](../intrinsics/compiler-intrinsics.md)
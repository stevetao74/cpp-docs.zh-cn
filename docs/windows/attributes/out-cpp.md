---
title: out （c + + COM 特性）
ms.date: 10/02/2018
f1_keywords:
- vc-attr.out
helpviewer_keywords:
- out attribute
ms.assetid: 5051b1bf-4949-4bf1-b82f-35e14f0f244b
ms.openlocfilehash: 15b82ddca42f9b70ac16538cea19f8aedd799c05
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50574438"
---
# <a name="out-c"></a>out (C++)

标识从被调用过程返回到调用过程（从服务器到客户端）的指针参数。

## <a name="syntax"></a>语法

```cpp
[out]
```

## <a name="remarks"></a>备注

**out** C++ 属性具有与 [out](/windows/desktop/Midl/out-idl) MIDL 属性相同的功能。

## <a name="example"></a>示例

请参阅 [bindable](bindable.md) 示例以了解 **out**的示例使用。

## <a name="requirements"></a>要求

### <a name="attribute-context"></a>特性上下文

|||
|-|-|
|**适用对象**|接口参数|
|**可重复**|否|
|**必需的特性**|无|
|**无效的特性**|无|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[IDL 特性](idl-attributes.md)<br/>
[参数特性](parameter-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[id](id.md)
---
title: public （c + + 特性） （c + + COM 属性）
ms.date: 10/02/2018
f1_keywords:
- vc-attr.public
helpviewer_keywords:
- public attribute
ms.assetid: c42e1fd5-6cb1-48fe-8a03-95f2a2e0137c
ms.openlocfilehash: d89df014beae5a62a035c3156b92d3337ecd2c14
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579330"
---
# <a name="public-c-attributes"></a>public（C++ 特性）

可确保即使它未从引用的.idl 文件中，一个 typedef 将转到类型库。

## <a name="syntax"></a>语法

```cpp
[public]
```

## <a name="remarks"></a>备注

**公共**c + + 属性具有相同的功能[公共](/windows/desktop/Midl/public)MIDL 特性。

## <a name="example"></a>示例

下面的代码演示如何使用**公共**属性：

```cpp
// cpp_attr_ref_public.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="ATLFIRELib")];
[export, public] typedef long MEMBERID;

[dispinterface, uuid(99999999-9999-9999-9999-000000000000)]
__interface IFireTabCtrl : IDispatch
{
   [id(2)] long procedure ([in, optional] VARIANT i);
};
```

## <a name="requirements"></a>要求

### <a name="attribute-context"></a>特性上下文

|||
|-|-|
|**适用对象**|**typedef**|
|**可重复**|否|
|**必需的特性**|无|
|**无效的特性**|无|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[IDL 特性](idl-attributes.md)<br/>
[Typedef、Enum、Union 和 Struct 特性](typedef-enum-union-and-struct-attributes.md)
---
title: library_block （c + + COM 属性）
ms.date: 10/02/2018
f1_keywords:
- vc-attr.library_block
helpviewer_keywords:
- library_block attribute
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
ms.openlocfilehash: 76e643cb45d8a87408015e6e0726e47d423147f1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459912"
---
# <a name="libraryblock"></a>library_block

将放置在 IDL 库块中的构造。

## <a name="syntax"></a>语法

```cpp
[library_block]
```

## <a name="remarks"></a>备注

在将库块中的构造，您确保，它将传递到类型库，而不考虑是否引用。 默认情况下，唯一的构造修改[组件类](coclass.md)， [dispinterface](dispinterface.md)，并[idl_module](idl-module.md)属性放置在库块。

## <a name="example"></a>示例

在下面的代码中，自定义接口置于库块。

```cpp
// cpp_attr_ref_library_block.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib")];
[object, library_block, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]
__interface IMyInterface {
   HRESULT f1();
};
```

## <a name="requirements"></a>要求

### <a name="attribute-context"></a>特性上下文

|||
|-|-|
|**适用对象**|任何位置|
|**可重复**|否|
|**必需的特性**|无|
|**无效的特性**|无|

有关详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>请参阅

[编译器特性](compiler-attributes.md)<br/>
[独立特性](stand-alone-attributes.md)
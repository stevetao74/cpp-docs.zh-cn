---
title: rdx （c + + COM 属性）
ms.date: 10/02/2018
f1_keywords:
- vc-attr.rdx
helpviewer_keywords:
- rdx attribute
ms.assetid: ff8e4312-c1ad-4934-bdaa-86f54409651e
ms.openlocfilehash: 0b21e94ce3c54c0234dd7883aac3ef5cadbbc009
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677872"
---
# <a name="rdx"></a>rdx

创建注册表项或修改现有的注册表项。

## <a name="syntax"></a>语法

```cpp
[ rdx(key, valuename=NULL, regtype) ]
```

### <a name="parameters"></a>参数

*key*<br/>
若要创建或打开密钥的名称。

*valuename*<br/>
（可选）指定要设置的值字段。 如果键中不存在具有此名称的值字段，将其添加。

*regtype*<br/>
要添加的注册表项的类型。 可以是以下之一： `text`， `dword`， `binary`，或`CString`。

## <a name="remarks"></a>备注

**Rdx** c + + 属性创建或修改现有的注册表项为 COM 组件。 该属性将 BEGIN_RDX_MAP 宏添加到实现的目标成员的对象。 `RegistryDataExchange`由于 BEGIN_RDX_MAP 宏，注入的函数可用于在注册表和数据成员之间传输数据

可以结合使用此特性[组件类](coclass.md)， [progid](progid.md)，或[vi_progid](vi-progid.md)属性或隐含其中之一的其他属性。

## <a name="requirements"></a>要求

### <a name="attribute-context"></a>特性上下文

|||
|-|-|
|**适用对象**|**类**或**结构**成员|
|**可重复**|否|
|**必需的特性**|无|
|**无效的特性**|无|

有关特性上下文的详细信息，请参见 [特性上下文](cpp-attributes-com-net.md#contexts)。

## <a name="example"></a>示例

以下代码添加到系统描述 CMyClass COM 组件调用 MyValue 注册表项。

```cpp
// cpp_attr_ref_rdx.cpp
// compile with: /LD /link /OPT:NOREF
#define _ATL_ATTRIBUTES
#include "atlbase.h"

[module (name="MyLib")];

class CMyClass {
public:
   CMyClass() {
      strcpy_s(m_sz, "SomeValue");
   }

   [ rdx(key = "HKCR\\MyApp.MyApp.1", valuename = "MyValue", regtype = "text")]
   char m_sz[256];
};
```

## <a name="see-also"></a>请参阅

[COM 特性](com-attributes.md)<br/>
[registration_script](registration-script.md)
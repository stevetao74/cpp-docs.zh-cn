---
title: CAccessor 类
ms.date: 11/04/2016
f1_keywords:
- ATL.CAccessor<T>
- ATL::CAccessor
- CAccessor
- ATL::CAccessor<T>
- ATL.CAccessor
helpviewer_keywords:
- CAccessor class
ms.assetid: b2ba959f-a686-46f3-8837-176248aef748
ms.openlocfilehash: 942a8e9eca7d09809594cbac1e4c14959aa96fbf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632670"
---
# <a name="caccessor-class"></a>CAccessor 类

表示一个访问器类型。

## <a name="syntax"></a>语法

```cpp
template <class T>
class CAccessor : public CAccessorBase, public T
```

### <a name="parameters"></a>参数

*T*<br/>
用户记录类。

## <a name="remarks"></a>备注

使用一条记录以静态方式绑定到数据源时。 该记录包含缓冲区。 此类支持多个访问器的行集。

当你知道的结构和数据库类型时，请使用此访问器类型。

如果您访问器包含指向内存的字段 (如`BSTR`或接口)，必须释放，调用成员函数[caccessorrowset:: Freerecordmemory](../../data/oledb/caccessorrowset-freerecordmemory.md)在下一步之前读取记录。

## <a name="requirements"></a>要求

**标头:** atldbcli.h

## <a name="see-also"></a>请参阅

[OLE DB 使用者模板](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 使用者模板参考](../../data/oledb/ole-db-consumer-templates-reference.md)
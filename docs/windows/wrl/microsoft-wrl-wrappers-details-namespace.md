---
title: Microsoft::WRL::Wrappers::Details 命名空间
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details
- internal/Microsoft::WRL::Details
- async/Microsoft::WRL::Details
- corewrappers/Microsoft::WRL::Wrappers::Details
- client/Microsoft::WRL::Details
- module/Microsoft::WRL::Details
- event/Microsoft::WRL::Details
helpviewer_keywords:
- Details namespace
ms.assetid: 6d3f04ac-9b53-4a82-a188-a85309ec34a4
ms.openlocfilehash: d02b19863ffa14e0edb3b1a96dceb936037743d3
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335796"
---
# <a name="microsoftwrlwrappersdetails-namespace"></a>Microsoft::WRL::Wrappers::Details 命名空间

支持 WRL 基础结构，不应在代码中直接使用。

## <a name="syntax"></a>语法

```cpp
namespace Microsoft::WRL::Wrappers::Details;
```

## <a name="members"></a>成员

### <a name="classes"></a>类

|名称|描述|
|----------|-----------------|
|[SyncLockT 类](synclockt-class.md)|表示可能需要排他的类型或共享资源的所有权。|
|[SyncLockWithStatusT 类](synclockwithstatust-class.md)|表示可能需要排他的类型或共享资源的所有权。|

### <a name="methods"></a>方法

|名称|描述|
|----------|-----------------|
|[CompareStringOrdinal 方法](comparestringordinal-method.md)|比较两个指定`HSTRING`对象，并返回一个整数，指示二者在排序顺序中的相对位置。|

## <a name="requirements"></a>要求

**标头：** corewrappers.h

**命名空间：** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>请参阅

[Microsoft::WRL::Wrappers 命名空间](microsoft-wrl-wrappers-namespace.md)
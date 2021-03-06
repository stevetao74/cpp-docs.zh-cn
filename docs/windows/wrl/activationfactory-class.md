---
title: ActivationFactory 类
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory
- module/Microsoft::WRL::ActivationFactory::ActivationFactory
- module/Microsoft::WRL::ActivationFactory::AddRef
- module/Microsoft::WRL::ActivationFactory::GetIids
- module/Microsoft::WRL::ActivationFactory::GetRuntimeClassName
- module/Microsoft::WRL::ActivationFactory::GetTrustLevel
- module/Microsoft::WRL::ActivationFactory::QueryInterface
- module/Microsoft::WRL::ActivationFactory::Release
helpviewer_keywords:
- Microsoft::WRL::ActivationFactory class
- Microsoft::WRL::ActivationFactory::ActivationFactory, constructor
- Microsoft::WRL::ActivationFactory::AddRef method
- Microsoft::WRL::ActivationFactory::GetIids method
- Microsoft::WRL::ActivationFactory::GetRuntimeClassName method
- Microsoft::WRL::ActivationFactory::GetTrustLevel method
- Microsoft::WRL::ActivationFactory::QueryInterface method
- Microsoft::WRL::ActivationFactory::Release method
ms.assetid: 5faddf1f-43b6-4f8a-97de-8c9d3ae1e1ff
ms.openlocfilehash: 8e5132f4a8711f6420cd9b52751550a96d10d8fc
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335728"
---
# <a name="activationfactory-class"></a>ActivationFactory 类

启用 Windows 运行时将激活的一个或多个类。

## <a name="syntax"></a>语法

```cpp
template <
    typename I0 = Details::Nil,
    typename I1 = Details::Nil,
    typename I2 = Details::Nil
>
class ActivationFactory :
    public Details::RuntimeClass<
        typename Details::InterfaceListHelper<
            IActivationFactory,
            I0,
            I1,
            I2,
            Details::Nil
        >::TypeT,
        RuntimeClassFlags<WinRt | InhibitWeakReference>,
        false
    >;
```

### <a name="parameters"></a>参数

*I0*<br/>
第零个接口中。

*I1*<br/>
第一个接口。

*I2*<br/>
第二个接口。

## <a name="remarks"></a>备注

`ActivationFactory` 提供的注册方法和的基本功能`IActivationFactory`接口。 `ActivationFactory` 此外可以提供自定义工厂实现。

以下代码段种演示了如何使用 ActivationFactory。

[!code-cpp[wrl-microsoft__wrl__activationfactory#1](../codesnippet/CPP/activationfactory-class_1.cpp)]

下面的代码段演示如何使用[实现](implements-structure.md)结构，以指定三个接口 Id。

`struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

名称                                                       | 描述
---------------------------------------------------------- | ------------------------------------------
[ActivationFactory::ActivationFactory](#activationfactory) | 初始化`ActivationFactory`类。

### <a name="public-methods"></a>公共方法

名称                                                           | 描述
-------------------------------------------------------------- | --------------------------------------------------------------------------------------------
[ActivationFactory::AddRef](#addref)                           | 递增当前引用计数`ActivationFactory`对象。
[ActivationFactory::GetIids](#getiids)                         | 检索已实现接口 ID 的数组。
[ActivationFactory::GetRuntimeClassName](#getruntimeclassname) | 获取运行时类名称的对象的当前`ActivationFactory`实例化。
[ActivationFactory::GetTrustLevel](#gettrustlevel)             | 获取对象的信任级别当前`ActivationFactory`实例化。
[ActivationFactory::QueryInterface](#queryinterface)           | 检索指向指定接口的指针。
[ActivationFactory::Release](#release)                         | 递减引用计数的当前`ActivationFactory`对象。

## <a name="inheritance-hierarchy"></a>继承层次结构

`I0`

`ChainInterfaces`

`I0`

`RuntimeClassBase`

`ImplementsHelper`

`DontUseNewUseMake`

`RuntimeClassFlags`

`RuntimeClassBaseT`

`RuntimeClass`

`ActivationFactory`

## <a name="requirements"></a>要求

**标头：** module.h

**命名空间：** Microsoft:: wrl

## <a name="activationfactory"></a>ActivationFactory::ActivationFactory

初始化`ActivationFactory`类。

```cpp
ActivationFactory();
```

## <a name="addref"></a>ActivationFactory::AddRef

递增当前引用计数`ActivationFactory`对象。

```cpp
STDMETHOD_(
   ULONG,
   AddRef
)();
```

### <a name="return-value"></a>返回值

如果成功，则为 S_OK；否则为描述失败的 HRESULT。

## <a name="getiids"></a>ActivationFactory::GetIids

检索已实现接口 ID 的数组。

```cpp
STDMETHOD(
   GetIids
)(_Out_ ULONG *iidCount, _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>参数

*iidCount*<br/>
此操作完成后中, 接口 Id 数*iid*数组。

*iids*<br/>
此操作完成后，已实现接口 ID 的数组。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK；否则为描述失败的 HRESULT。 E_OUTOFMEMORY 是可能的失败 HRESULT。

## <a name="getruntimeclassname"></a>ActivationFactory::GetRuntimeClassName

获取运行时类名称的对象的当前`ActivationFactory`实例化。

```cpp
STDMETHOD(
   GetRuntimeClassName
)(_Out_ HSTRING* runtimeName);
```

### <a name="parameters"></a>参数

*runtimeName*<br/>
此操作完成后，包含对象的运行时类名称的字符串的句柄的当前`ActivationFactory`实例化。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK；否则为描述失败的 HRESULT。

## <a name="gettrustlevel"></a>ActivationFactory::GetTrustLevel

获取对象的信任级别当前`ActivationFactory`实例化。

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

### <a name="parameters"></a>参数

*trustLvl*<br/>
在运行时的信任级别完成此操作后，类，该类`ActivationFactory`实例化。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK否则，将发出断言错误并*trustLvl*设置为`FullTrust`。

## <a name="queryinterface"></a>ActivationFactory::QueryInterface

检索指向指定接口的指针。

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>参数

*riid*<br/>
接口 ID。

*ppvObject*<br/>
完成此操作后，指向由参数指定的接口的指针*riid*。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK；否则为描述失败的 HRESULT。

## <a name="release"></a>ActivationFactory::Release

递减引用计数的当前`ActivationFactory`对象。

```cpp
STDMETHOD_(
   ULONG,
   Release
)();
```

### <a name="return-value"></a>返回值

如果成功，则为 S_OK；否则为描述失败的 HRESULT。

---
title: ArgTraits 结构
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraits
- event/Microsoft::WRL::Details::ArgTraits::args
helpviewer_keywords:
- Microsoft::WRL::Details::ArgTraits structure
- Microsoft::WRL::Details::ArgTraits::args constant
ms.assetid: 58ae4115-c1bc-48c8-b01b-e60554841c30
ms.openlocfilehash: 17109508cf99888ccde79be39a41c5361da24c6e
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335554"
---
# <a name="argtraits-structure"></a>ArgTraits 结构

支持 WRL 基础结构，不应在代码中直接使用。

## <a name="syntax"></a>语法

```cpp
template<typename TMemberFunction>
struct ArgTraits;

template<typename TDelegateInterface>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(void)>;

template<typename TDelegateInterface, typename TArg1>
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1)>;

template<typename TDelegateInterface, typename TArg1, typename TArg2>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7,
    typename TArg8
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8)>;

template<
    typename TDelegateInterface,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7,
    typename TArg8,
    typename TArg9
>
struct ArgTraits<
    HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)
             (TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8, TArg9)>;
```

### <a name="parameters"></a>参数

*TMemberFunction*<br/>
ArgTraits 结构，它不能与任何匹配的 Typename 参数`Invoke`方法签名。

*TDelegateInterface*<br/>
委托的接口。

*TArg1*<br/>
第一个参数的类型`Invoke`方法。

*TArg2*<br/>
第二个自变量的类型`Invoke`方法。

*TArg3*<br/>
第三个自变量的类型`Invoke`方法。

*TArg4*<br/>
第四个自变量的类型`Invoke`方法。

*TArg5*<br/>
第五个自变量的类型`Invoke`方法。

*TArg6*<br/>
第六个自变量的类型`Invoke`方法。

*TArg7*<br/>
第七个自变量的类型`Invoke`方法。

*TArg8*<br/>
第八个自变量的类型`Invoke`方法。

*TArg9*<br/>
第九个自变量的类型`Invoke`方法。

## <a name="remarks"></a>备注

`ArgTraits`结构接口和具有指定的数目的参数的匿名成员函数声明指定的委托。

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

名称       | 描述
---------- | ----------------------
`Arg1Type` | TArg1 typedef。
`Arg2Type` | TArg2 typedef。
`Arg3Type` | TArg3 typedef。
`Arg4Type` | TArg4 typedef。
`Arg5Type` | TArg5 typedef。
`Arg6Type` | TArg6 typedef。
`Arg7Type` | TArg7 typedef。
`Arg8Type` | TArg8 typedef。
`Arg9Type` | TArg9 typedef。

### <a name="public-constants"></a>公共常量

name                     | 描述
------------------------ | ---------------------------------------------------------------------------------------
[ArgTraits::args](#args) | 中保留的参数的数目计数`Invoke`委托接口的方法。

## <a name="inheritance-hierarchy"></a>继承层次结构

`ArgTraits`

## <a name="requirements"></a>要求

**标头：** event.h

**命名空间：** Microsoft::WRL::Details

## <a name="args"></a>ArgTraits::args

支持 WRL 基础结构，不应在代码中直接使用。

```cpp
static const int args = -1;
```

### <a name="remarks"></a>备注

中保留的参数的数目计数`Invoke`委托接口的方法。 当`args`等于-1，可以有没有匹配项`Invoke`方法签名。

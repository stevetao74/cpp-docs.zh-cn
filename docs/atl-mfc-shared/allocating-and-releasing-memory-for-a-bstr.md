---
title: 为 BSTR 分配和释放内存
ms.date: 11/04/2016
f1_keywords:
- bstr
helpviewer_keywords:
- BSTRs, memory allocation
- memory deallocation, string memory
- memory [C++], releasing
- memory allocation, BSTRs
- memory deallocation, BSTR memory
- strings [C++], releasing
ms.assetid: 98041e29-3442-4a02-b425-7a4a13e9cc84
ms.openlocfilehash: cfa921758122dfadb7b008740a14e352456a180f
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2018
ms.locfileid: "51518185"
---
# <a name="allocating-and-releasing-memory-for-a-bstr"></a>为 BSTR 分配和释放内存

当你创建`BSTR`s 和 COM 对象之间传递它们，您必须小心地处理它们使用，以避免内存泄漏的内存。 当`BSTR`保持界面中的，您必须释放其内存是完成。 但是，当`BSTR`带接口的传递，接收对象有责任在其内存管理。

一般情况下，分配和释放内存的规则分配为`BSTR`s 如下所示：

- 当您调用到所需的函数`BSTR`自变量，您必须分配的内存`BSTR`在调用之前和之后将其释放。 例如：

   [!code-cpp[NVC_ATLMFC_Utilities#192](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_1.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#193](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_2.cpp)]

- 当您调用一个函数，返回到`BSTR`，必须自行释放字符串。 例如：

   [!code-cpp[NVC_ATLMFC_Utilities#194](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_3.cpp)]

   [!code-cpp[NVC_ATLMFC_Utilities#195](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_4.cpp)]

- 当实现一个函数，返回`BSTR`、 分配字符串，但不是释放它。 接收该函数会释放内存。 例如：

   [!code-cpp[NVC_ATLMFC_Utilities#196](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_5.cpp)]

## <a name="see-also"></a>请参阅

[字符串 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring)<br/>
[SysAllocString](/windows/desktop/api/oleauto/nf-oleauto-sysallocstring)<br/>
[SysFreeString](/windows/desktop/api/oleauto/nf-oleauto-sysfreestring)


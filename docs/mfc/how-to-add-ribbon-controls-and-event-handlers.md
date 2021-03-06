---
title: 如何：添加功能区控件和事件处理程序
ms.date: 11/04/2016
helpviewer_keywords:
- event handlers [MFC], adding
- ribbon controls [MFC], adding
ms.assetid: b31f25bc-ede7-49c3-9e3c-dffe4e174a69
ms.openlocfilehash: 356358e5fd5ac4f3f7511f178ca304e9ab7eff86
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2018
ms.locfileid: "51518393"
---
# <a name="how-to-add-ribbon-controls-and-event-handlers"></a>如何：添加功能区控件和事件处理程序

功能区控件是元素，例如按钮和组合框中，添加到面板。 面板，显示的一组相关控件的功能区栏区域。

在本主题中，将打开功能区设计器，添加一个按钮，然后链接将显示"Hello World"的事件。

### <a name="to-open-the-ribbon-designer"></a>若要打开功能区设计器

1. 在 Visual Studio 中，在**视图**菜单上，单击**资源视图**。

1. 在中**资源视图**，双击要在设计图面上显示的功能区资源。

### <a name="to-add-a-button-and-an-event-handler"></a>若要添加一个按钮和一个事件处理程序

1. 从**工具栏**，单击**按钮**并将其拖到设计图面中的一个面板。

1. 右键单击该按钮，然后单击**添加事件处理程序**。

1. 在中**事件处理程序向导**，确认默认设置，然后单击**添加和编辑**。 有关详细信息，请参阅[事件处理程序向导](../ide/event-handler-wizard.md)。

1. 在代码编辑器中，将以下代码添加到处理程序函数：

```
    MessageBox((LPCTSTR)L"Hello World");
```

## <a name="see-also"></a>请参阅

[RibbonGadgets 示例： 功能区的小工具应用程序](../visual-cpp-samples.md)<br/>
[功能区设计器 (MFC)](../mfc/ribbon-designer-mfc.md)


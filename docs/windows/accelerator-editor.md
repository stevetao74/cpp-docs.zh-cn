---
title: 快捷键编辑器 （c + +）
ms.date: 11/04/2016
f1_keywords:
- vc.editors.accelerator.F1
helpviewer_keywords:
- accelerator tables [C++], editing
- tables [C++], accelerator key
- accelerator keys [C++]
- resource editors [C++], Accelerator editor
- keyboard shortcuts [C++], Accelerator editor
ms.assetid: 013c30b6-5d61-4f1c-acef-8bd15bed7060
ms.openlocfilehash: fdb2d9cf0954142da990a0a9f995cb482060345d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621489"
---
# <a name="accelerator-editor-c"></a>快捷键编辑器 （c + +）

快捷键对应表是包含一系列加速键 （也称为键盘快捷方式） 的 c + + Windows 资源和与之关联的命令标识符。 一个程序可以拥有多个快捷键对应表。

通常情况下，快捷键用作程序命令的键盘快捷键，也可用于菜单或工具栏。 但是，快捷键对应表可用于为没有关联用户界面对象的命令定义组合键。

可以使用 [类视图](/visualstudio/ide/viewing-the-structure-of-code) 将快捷键命令与代码挂接。

与**Accelerator**编辑器，你可以：

- [设置快捷键属性](../windows/setting-accelerator-properties.md)

- [将快捷键与菜单项关联](../windows/associating-an-accelerator-key-with-a-menu-item.md)

- [编辑快捷键对应表](../windows/editing-accelerator-tables.md)

- [使用预定义快捷键](../windows/predefined-accelerator-keys.md)

   > [!TIP]
   > 使用时**Accelerator**编辑器中，你可以右击以显示常用命令的快捷菜单。 可用命令取决于指针所指向的内容。

   > [!NOTE]
   > Windows 不允许创建空快捷键对应表。 如果创建的快捷键对应表中没有任何条目，在保存表时会被自动删除。

有关将资源添加到托管项目的信息，请参阅[桌面应用中的资源](/dotnet/framework/resources/index)中 *.NET Framework 开发人员指南*。 有关手动将资源文件添加到托管项目、 访问资源、 显示静态资源和将资源字符串分配给属性的信息，请参阅[桌面应用中创建资源文件](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)。 全球化和本地化的托管应用中的资源的信息，请参阅[Globalizing and Localizing.NET Framework Applications](/dotnet/standard/globalization-localization/index)。

## <a name="requirements"></a>要求

Win32

## <a name="see-also"></a>请参阅

[资源编辑器](../windows/resource-editors.md)
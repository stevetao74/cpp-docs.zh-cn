---
title: 错误 C1084
ms.date: 11/04/2016
f1_keywords:
- C1084
helpviewer_keywords:
- C1084
ms.assetid: b2f273ef-3a14-4d5f-8ce0-7a11a0388fe6
ms.openlocfilehash: 8c90616165a7b47d4251ace998fd49c613f244b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548039"
---
# <a name="fatal-error-c1084"></a>错误 C1084

无法读取 filetype 文件：“file”: 消息

此错误通常是由编译器无法执行内部系统 API 调用造成的。 如果遇到此错误，则所显示的消息通常通过以下任一方法生成[_wcserror_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)或[FormatMessage](/windows/desktop/api/winbase/nf-winbase-formatmessage)。

执行以下步骤可帮助解决 C1084 错误：

- 请确保指定的文件存在。

- 请确保设置了访问指定文件所需的相应权限。

- 请确保命令行语法符合下所述的规则[编译器命令行语法](../../build/reference/compiler-command-line-syntax.md)。

- 请确保环境变量**TMP**并**TEMP**为正确的组，以及适当的权限才能访问这些环境变量所引用的目录。 通过所引用的驱动器，请也确保**TMP**并**TEMP**环境变量包含足够的可用空间量。

- 如果消息指出“文件号错误”，说明指定的文件在后台进行编译的同时，可能已在前台关闭。

执行上面的诊断后，请执行干净的生成。
---
title: 创建 .Sbr 文件
ms.date: 11/04/2016
helpviewer_keywords:
- SBR files
- BSCMAKE, input files
- .sbr files
- source browser files
- local symbols in browse information
- symbols
ms.assetid: bdb4b93c-a88a-441a-84fd-01087d03be25
ms.openlocfilehash: 63f007e567f3c1db556ba6a7f0c1a354c449f31b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500995"
---
# <a name="creating-an-sbr-file"></a>创建 .Sbr 文件

BSCMAKE 的输入的文件是.sbr 文件。 编译器创建的每个对象文件 (.obj) 对其进行编译的.sbr 文件。 当生成或更新你的浏览信息文件时，所有的.sbr 文件为你的项目必须是可在磁盘上。

若要创建的.sbr 文件与所有可能的信息，请指定[/FR](../../build/reference/fr-fr-create-dot-sbr-file.md)。

若要创建不包含本地符号的.sbr 文件，请指定[/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md)。 如果.sbr 文件包含本地符号，则可以仍省略它们从.bsc 文件使用 BSCMAKE 的[/El 选项](../../build/reference/bscmake-options.md)`.`

无需执行完整编译，可以创建的.sbr 文件。 例如，可以指定向编译器执行语法检查，并仍生成的.sbr 文件，如果指定 /FR 或 /Fr./Zs 选项

生成过程可能更有效，如果先压缩.sbr 文件以移除未引用的定义。 编译器会自动打包的.sbr 文件。

## <a name="see-also"></a>请参阅

[生成 .Bsc 文件](../../build/reference/building-a-dot-bsc-file.md)
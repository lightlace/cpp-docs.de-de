---
title: Linkertoolwarnung Lnk4105 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4105
dev_langs:
- C++
helpviewer_keywords:
- LNK4105
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ffdd8953e08f38d36bdfc2e68ad6cb8e06fb85b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33304413"
---
# <a name="linker-tools-warning-lnk4105"></a>Linkertoolwarnung LNK4105
kein Argument angegeben mit der Option 'Option'; Option wird ignoriert.  
  
 Diese Warnung tritt nur auf, wenn die [/LIBPATH](../../build/reference/libpath-additional-libpath.md) Option festgelegt ist. Wenn kein Verzeichnis mit dieser Option angegeben wird, kann der Linker die Option ignoriert und für diese Warnung generiert.  
  
 Wenn Sie nicht die vorhandenen environmental bibliothekseinstellungen außer Kraft setzen müssen, entfernen Sie die/LIBPATH-Option in der Linker-Befehlszeile. Wenn Sie einen alternativen Suchpfad für Bibliotheken verwenden möchten, geben Sie den alternativen Pfad nach der Option/LIBPATH.  
  
## <a name="example"></a>Beispiel  
  
```  
link /libpath:c:\filepath\lib bar.obj  
```  
  
 leitet den Linker an, für die erforderlichen Bibliotheken in Suchen `c:\filepath\lib` vor dem in die Standardspeicherorte suchen.
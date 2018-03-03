---
title: Linkertoolwarnung Lnk4105 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4105
dev_langs:
- C++
helpviewer_keywords:
- LNK4105
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 913a6da056908def8df5aab1c2425ef9a187c1e2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
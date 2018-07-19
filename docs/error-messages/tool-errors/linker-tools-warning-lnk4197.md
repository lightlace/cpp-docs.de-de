---
title: Linkertoolwarnung Lnk4197 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4197
dev_langs:
- C++
helpviewer_keywords:
- LNK4197
ms.assetid: 8a976fd7-a74b-4c83-ab66-a9e7d7073c4a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dfef7f0fe2d9cd50fa6a18ad682c3e4d80df99c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300831"
---
# <a name="linker-tools-warning-lnk4197"></a>Linkertoolwarnung LNK4197
Export 'Exportname ' wurde mehrmals angegeben; Mithilfe der ersten Spezifikation  
  
 Ein Export wird in mehreren angegeben und auf unterschiedliche Weise. Der Linker verwendet die erste Spezifikation und der Rest wird ignoriert.  
  
 Wenn Sie die C-Laufzeitbibliothek neu sind, können Sie diese Meldung ignorieren.  
  
 Wenn ein Export genau die gleiche Weise mehrere Male angegeben wird, wird der Linker keine Warnung ausgegeben.  
  
 Beispielsweise würde eine DEF-Datei mit folgendem Inhalt diese Warnung:  
  
```  
EXPORTS  
   functioname      NONAME  
   functioname      @10  
```  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Der gleiche Export angegeben ist sowohl in der Befehlszeile (durch Export:) und in der DEF-Datei  
  
2.  Der gleiche Export wird in der DEF-Datei mit verschiedenen Attributen zweimal aufgeführt.
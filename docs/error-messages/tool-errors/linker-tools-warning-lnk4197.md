---
title: Linkertoolwarnung Lnk4197 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4197
dev_langs:
- C++
helpviewer_keywords:
- LNK4197
ms.assetid: 8a976fd7-a74b-4c83-ab66-a9e7d7073c4a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b1fadbf2ba5b18004f0e89142c88a68437842a92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
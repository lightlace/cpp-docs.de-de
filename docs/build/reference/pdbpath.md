---
title: -PDBPATH | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /pdbpath
dev_langs:
- C++
helpviewer_keywords:
- .pdb files, path
- -PDBPATH dumpbin option
- /PDBPATH dumpbin option
- PDBPATH dumpbin option
- PDB files, path
ms.assetid: ccf67dcd-0b23-4250-ad47-06c48acbe82b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0ccbcedbf9cdd376fa7d9bced5c9d49542cee9f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="pdbpath"></a>/PDBPATH
```  
/PDBPATH[:VERBOSE] filename  
```  
  
## <a name="remarks"></a>Hinweise  
 Dabei gilt:  
  
 *filename*  
 Der Name der .dll oder .exe-Datei, die für die zugehörige PDB-Datei gefunden werden sollen.  
  
 VERBOSE (optional)  
 Meldet alle Verzeichnisse, in dem versucht wurde, die PDB-Datei zu suchen.  
  
## <a name="remarks"></a>Hinweise  
 / PDBPATH durchsucht Ihren Computer entlang der gleichen Pfade, die der Debugger keine PDB-Datei suchen würde, und meldet, die ggf. die Datei im angegebenen PDB-Dateien entsprechen *Filename*.  
  
 Wenn Sie Visual Studio-Debugger verwenden, können darauf zurückzuführen, dass der Debugger keine PDB-Datei für eine andere Version der Datei verwendet wird, die Sie Debuggen ein Problem auftreten.  
  
 / PDBPATH sucht nach den folgenden Pfaden PDB-Dateien:  
  
-   Überprüfen Sie den Speicherort, in dem die ausführbare Datei befindet.  
  
-   Überprüfen Sie den Speicherort der PDB-Datei in die ausführbare Datei geschrieben. Dies ist normalerweise der Speicherort, zu dem Zeitpunkt, den das Bild verknüpft wurde.  
  
-   Überprüfen Sie entlang den Suchpfad, der in der Visual Studio-IDE konfiguriert.  
  
-   Überprüfen Sie entlang der Pfade in der _NT_SYMBOL_PATH und _NT_ALT_SYMBOL_PATH Umgebungsvariablen.  
  
-   Überprüfen Sie im Windows-Verzeichnis.  
  
## <a name="see-also"></a>Siehe auch  
 [DUMPBIN-Optionen](../../build/reference/dumpbin-options.md)   
 [/ PDBALTPATH (mit alternativen PDB-Pfad)](../../build/reference/pdbaltpath-use-alternate-pdb-path.md)
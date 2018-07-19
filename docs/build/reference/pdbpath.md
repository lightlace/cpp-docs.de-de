---
title: -PDBPATH | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 274c4a3742d99b1e4702ed332206b78dacebccbd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373667"
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
 [/PDBALTPATH (Alternativen PDB-Pfad verwenden)](../../build/reference/pdbaltpath-use-alternate-pdb-path.md)
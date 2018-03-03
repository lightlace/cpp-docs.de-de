---
title: -ALLOWISOLATION (Manifestsuche) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /ALLOWISOLATION
- VC.Project.VCLinkerTool.AllowIsolation
dev_langs:
- C++
helpviewer_keywords:
- -ALLOWISOLATION linker option
- /ALLOWISOLATION linker option
ms.assetid: 6d41851e-b3c1-4bdf-beaa-031773089d6f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d0ca939021a6fc530b11c6ec66fc74cc012da1c9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="allowisolation-manifest-lookup"></a>/ALLOWISOLATION (Manifestsuche)
Gibt das Verhalten bei der Manifestsuche an.  
  
## <a name="syntax"></a>Syntax  
  
```  
/ALLOWISOLATION[:NO]  
```  
  
## <a name="remarks"></a>Hinweise  
 **/ALLOWISOLATION:No** DLLs geladen, als wäre kein Manifest und führt dazu, dass den Linker Festlegen der `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` bit im optionalen-Headers `DllCharacteristics` Feld.  
  
 **/ ALLOWISOLATION** bewirkt, dass das Betriebssystem, Suchvorgänge und-Ladevorgänge durchführt.  
  
 **/ ALLOWISOLATION** ist die Standardeinstellung.  
  
 Wenn Isolation für eine ausführbare Datei deaktiviert ist, wird das Windows-Ladeprogramm nicht versucht, ein Anwendungsmanifest für den neu erstellten Prozess gefunden. Der neue Prozess keinen Standard-Aktivierungskontext, auch wenn es ein Manifest in die ausführbare Datei oder eine platzierten im selben Verzeichnis wie die ausführbare Datei mit dem Namen *Name der ausführbaren Datei***. exe.manifest**.  
  
 Weitere Informationen finden Sie unter [Manifestdateienreferenz](http://msdn.microsoft.com/library/aa375632).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie die **Konfigurationseigenschaften** Knoten.  
  
3.  Erweitern Sie die **Linker** Knoten.  
  
4.  Wählen Sie die **Manifestdatei** Eigenschaftenseite.  
  
5.  Ändern der **Isolation zulassen** Eigenschaft.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)
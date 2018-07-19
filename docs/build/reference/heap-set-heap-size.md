---
title: -HEAP (Heapgröße festlegen) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.HeapCommitSize
- /heap
- VC.Project.VCLinkerTool.HeapReserveSize
dev_langs:
- C++
helpviewer_keywords:
- -HEAP linker option
- heap allocation, setting heap size
- /HEAP linker option
- HEAP linker option
ms.assetid: a3f71927-7f1d-492c-9fdb-dfccb1a043da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b968b3c8e9063eea897c70d4ae2a62a9a232d6b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374556"
---
# <a name="heap-set-heap-size"></a>/HEAP (Heapgröße festlegen)
```  
/HEAP:reserve[,commit]  
```  
  
## <a name="remarks"></a>Hinweise  
 Durch die Option legt die Größe des Heap in Bytes fest. Diese Option ist nur für die Verwendung auf, wenn eine .exe-Datei zu erstellen.  
  
 Die *reservieren* Argument gibt die gesamte Heapreservierung im virtuellen Speicher an. Die Standard-Heapgröße beträgt 1 MB. Der Linker rundet den angegebenen Wert in der nächsten 4 Bytes.  
  
 Das optionale `commit` -Argument gibt die Menge an physikalischem Arbeitsspeicher, zu einem Zeitpunkt belegen. Die Zusicherung von virtuellem Speicher bewirkt die Belegung von Speicher in der Auslagerungsdatei. Eine höhere `commit` -Wert spart Zeit, wenn die Anwendung mehr Heapspeicher benötigt, erhöht aber die arbeitsspeicheranforderungen und möglicherweise die Startzeit.  
  
 Geben Sie die *reservieren* und `commit` Werten in Decimal oder C-Notation.  
  
 Diese Funktion steht auch über eine Moduldefinitionsdatei mit [HEAPSIZE](../../build/reference/heapsize.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die **System** Eigenschaftenseite.  
  
4.  Ändern der **Heapgröße Commit** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Weitere Informationen finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapReserveSize%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapCommitSize%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)
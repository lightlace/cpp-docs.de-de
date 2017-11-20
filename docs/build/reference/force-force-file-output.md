---
title: -FORCE (DateiAusgabe erzwingen) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.ForceLink
- /force
dev_langs: C++
helpviewer_keywords:
- FORCE linker option
- file output in linker
- /FORCE linker option
- -FORCE linker option
ms.assetid: b1e9a218-a5eb-4e60-a4a4-65b4be15e5da
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2990ff88e896c7cafb3ff8eb2d9acf149d7a90c0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="force-force-file-output"></a>/FORCE (Dateiausgabe erzwingen)
```  
/FORCE:[MULTIPLE|UNRESOLVED]  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Option/Force weist den Linker an eine gültige .exe-Datei zu erstellen oder DLL selbst wenn ein Symbol, aber nicht verwiesen wird definiert oder mehrfach definiert ist.  
  
 Die Option/Force kann optionale Argumente:  
  
-   Verwenden Sie/Force: Multiple, um eine Ausgabedatei erstellt, und zwar unabhängig davon, ob LINK mehr als eine Definition für ein Symbol findet.  
  
-   Verwenden Sie/Force: eine Ausgabedatei erstellt, und zwar unabhängig davon, ob LINK ein nicht definiertes Symbol findet nicht AUFGELÖST. / FORCE: nicht AUFGELÖSTE wird ignoriert, wenn das Einstiegspunktsymbol nicht aufgelöst ist.  
  
 / FORCE ohne Argumente impliziert mehrfach und nicht aufgelöst werden.  
  
 Eine mit dieser Option erstellte Datei kann nicht wie erwartet ausgeführt. Der Linker wird nicht inkrementell verknüpft werden, wenn die Option/Force angegeben wird.  
  
 Wenn ein Modul mit kompiliert wird **"/ CLR"**, **/ERZWINGEN** ein Bild wird nicht erstellt werden.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Geben Sie die Option in der **Zusatzoptionen** Feld.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)
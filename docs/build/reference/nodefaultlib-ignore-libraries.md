---
title: -NODEFAULTLIB (Bibliotheken ignorieren) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.OVERWRITEAllDefaultLibraries
- VC.Project.VCLinkerTool.OVERWRITEDefaultLibraryNames
- /nodefaultlib
dev_langs:
- C++
helpviewer_keywords:
- default libraries, removing
- -NODEFAULTLIB linker option
- libraries, ignore
- NODEFAULTLIB linker option
- /NODEFAULTLIB linker option
- ignore libraries linker option
ms.assetid: 7270b673-6711-468e-97a7-c2925ac2be6e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 51caac10218d5f4d1787b2256875001ac32dc2b9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="nodefaultlib-ignore-libraries"></a>/NODEFAULTLIB (Bibliotheken ignorieren)
```  
/NODEFAULTLIB[:library]   
```  
  
## <a name="remarks"></a>Hinweise  
 Dabei gilt:  
  
 *Bibliothek*  
 Eine Bibliothek, die den Linker an, beim Auflösen externer Verweise ignoriert werden sollen.  
  
## <a name="remarks"></a>Hinweise  
 Die/NODEFAULTLIB-Option weist den Linker an, eine oder mehrere Standardbibliotheken aus der Liste der Bibliotheken zu entfernen, die beim Auflösen externer Verweise durchsucht.  
  
 Verwenden Sie zum Erstellen einer OBJ-Datei, die keine Verweise auf Standardbibliotheken enthält [Zl (weglassen Standardbibliotheksnamen)](../../build/reference/zl-omit-default-library-name.md).  
  
 Standardmäßig entfernt/NODEFAULTLIB alle Standardbibliotheken aus der Liste der Bibliotheken, die beim Auflösen externer Verweise durchsucht. Das optionale *Bibliothek* Parameter können Sie eine oder mehrere angegebene Bibliotheken aus der Liste der Bibliotheken entfernen beim Auflösen externer Verweise durchsucht. Geben Sie eine/NODEFAULTLIB-Option für jede Bibliothek, die Sie ausschließen möchten.  
  
 Der Linker löst Verweise auf externe Definitionen durch suchen zuerst in Bibliotheken, die Sie explizit angeben, und klicken Sie dann im Standardmodus Bibliotheken, die mit der Option-Option angegebene und Standardbibliotheken, die in der OBJ-Dateien.  
  
 / NODEFAULTLIB:*Bibliothek* überschreibt [Option:](../../build/reference/defaultlib-specify-default-library.md)*Bibliothek* bei dem *Bibliothek* Name wird in beiden angegeben.  
  
 Bei Verwendung von/NODEFAULTLIB z. B. das Programm ohne die C-Laufzeitbibliothek, erstellen Sie möglicherweise auch [/Entry](../../build/reference/entry-entry-point-symbol.md) Einstiegspunkt (Funktion) im Programm angeben. Weitere Informationen finden Sie unter [CRT Library Features (CRT-Bibliotheksfunktionen)](../../c-runtime-library/crt-library-features.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die **Eingabe**Eigenschaftenseite.  
  
4.  Wählen Sie die **alle Standardbibliotheken ignorieren** Eigenschaft, oder geben Sie eine Liste der Bibliotheken, die ignoriert werden sollen die **Bibliothek ignorieren** Eigenschaft. Die **Befehlszeile** Eigenschaftenseite wird die Auswirkung der Änderungen, die Sie, um diese Eigenschaften vornehmen anzuzeigen.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Weitere Informationen finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreDefaultLibraryNames%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreAllDefaultLibraries%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)
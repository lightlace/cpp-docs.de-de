---
title: "/NODEFAULTLIB (Bibliotheken ignorieren)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.IgnoreAllDefaultLibraries"
  - "VC.Project.VCLinkerTool.IgnoreDefaultLibraryNames"
  - "/nodefaultlib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/NODEFAULTLIB (Linkeroption)"
  - "Standardbibliotheken, Entfernen"
  - "Bibliotheken ignorieren (Linkeroption)"
  - "Bibliotheken, Ignorieren"
  - "NODEFAULTLIB (Linkeroption)"
  - "-NODEFAULTLIB (Linkeroption)"
ms.assetid: 7270b673-6711-468e-97a7-c2925ac2be6e
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# /NODEFAULTLIB (Bibliotheken ignorieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/NODEFAULTLIB[:library]   
```  
  
## Hinweise  
 Hierbei ist:  
  
 *library*  
 eine Bibliothek, die vom Linker beim Auflösen externer Verweise ignoriert werden soll.  
  
## Hinweise  
 Die \/NODEFAULTLIB\-Option weist den Linker an, mindestens eine Standardbibliothek aus der Liste der Bibliotheken, die durchsucht werden, zu entfernen, wenn externe Verweise aufgelöst werden.  
  
 Verwenden Sie [\/Zl \(Kein Standardbibliotheksname\)](../../build/reference/zl-omit-default-library-name.md), um eine OBJ\-Datei zu erstellen, die keine Verweise auf Standardbibliotheken enthält.  
  
 Standardmäßig entfernt **\/NODEFAULTLIB** alle Standardbibliotheken aus der Liste der Bibliotheken, die beim Auflösen externer Verweise durchsucht werden.  Der optionale Parameter *library* ermöglicht es, eine oder mehrere angegebene Bibliotheken aus der Liste der Bibliotheken zu entfernen, die beim Auflösen externer Verweise durchsucht werden.  Geben Sie für jede auszuschließende Bibliothek eine **\/NODEFAULTLIB**\-Option an.  
  
 Der Linker löst Verweise auf externe Definitionen auf, indem zuerst die in der Befehlszeile angegebenen Bibliotheken durchsucht werden, dann die mit der Option **\/DEFAULTLIB** festgelegten Standardbibliotheken und danach die in den OBJ\-Dateien genannten Standardbibliotheken.  
  
 Mit **\/NODEFAULTLIB**:*library* wird [\/DEFAULTLIB:](../../build/reference/defaultlib-specify-default-library.md)*library* überschrieben, wenn in beiden Optionen dieselbe *library* verwendet wird.  
  
 Wenn beim Erstellen des Programms ohne C\-Laufzeitbibliothek beispielsweise **\/NODEFAULTLIB** verwendet wird, müssen Sie gegebenenfalls auch [\/ENTRY](../../build/reference/entry-entry-point-symbol.md) angeben, um den Einstiegspunkt \(die Funktion\) im Programm festzulegen.  Weitere Informationen finden Sie unter [CRT\-Bibliotheksfunktionen](../../c-runtime-library/crt-library-features.md).  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Eingabe**.  
  
4.  Wählen Sie die Eigenschaft **Standardbibliotheken ignorieren** aus, oder geben Sie in der Eigenschaft **Bibliothek ignorieren** eine Liste von Bibliotheken an, die ignoriert werden sollen.  Auf der Eigenschaftenseite **Befehlszeile** werden die Auswirkungen der in diesen Eigenschaften vorgenommenen Änderungen angezeigt.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Weitere Informationen finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreDefaultLibraryNames*> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreAllDefaultLibraries*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)
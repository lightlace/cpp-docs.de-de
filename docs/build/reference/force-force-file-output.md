---
title: "/FORCE (Dateiausgabe erzwingen) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.ForceLink"
  - "/force"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FORCE (Linkeroption)"
  - "Dateiausgabe im Linker"
  - "FORCE (Linkeroption)"
  - "-FORCE (Linkeroption)"
ms.assetid: b1e9a218-a5eb-4e60-a4a4-65b4be15e5da
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /FORCE (Dateiausgabe erzwingen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/FORCE:[MULTIPLE|UNRESOLVED]  
```  
  
## Hinweise  
 Die Option **\/FORCE** weist den Linker an, eine gültige EXE\-Datei oder DLL zu erstellen, auch wenn auf ein Symbol verwiesen wird, das nicht oder mehrfach definiert ist.  
  
 Die Option **\/FORCE** akzeptiert auch optionale Argumente:  
  
-   Verwenden Sie \/FORCE:MULTIPLE, um eine Ausgabedatei zu erstellen, mit der Information, ob LINK mehr als eine Definition für ein Symbol findet oder nicht.  
  
-   Verwenden Sie \/FORCE:UNRESOLVED, um eine Ausgabedatei zu erstellen mit der Information, ob LINK ein nicht definiertes Symbol findet oder nicht. \/FORCE:UNRESOLVED wird ignoriert, wenn das Einstiegspunktsymbol nicht aufgelöst ist.  
  
 \/FORCE ohne Argumente impliziert sowohl mehrfach als auch nicht aufgelöst.  
  
 Eine mit dieser Option erstellte Datei wird möglicherweise nicht wie erwartet ausgeführt.  Der Linker führt kein inkrementelles Verknüpfen durch, wenn die Option **\/FORCE** angegeben wird.  
  
 Wenn ein Modul mit **\/clr** kompiliert wird, erstellt **\/FORCE** kein Bild.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Geben Sie die Option im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)
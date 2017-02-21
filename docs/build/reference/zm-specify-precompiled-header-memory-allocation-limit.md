---
title: "/Zm (Begrenzung der Speicherzuweisung f&#252;r vorkompilierten Header festlegen) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/zm"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pch-Dateien, Speicherreservierungsgrenze"
  - "/Zm (Compileroption) [C++]"
  - "cl.exe-Compiler, Speicherreservierungsgrenze"
  - "Speicherreservierung, Speicherreservierungsgrenze (Compileroption)"
  - "PCH-Dateien, Speicherreservierungsgrenze"
  - "Vorkompilierte Headerdateien, Speicherreservierungsgrenze"
  - "Begrenzung der Speicherzuweisung für vorkompilierten Header festlegen (Compileroption)"
  - "Zm (Compileroption) [C++]"
  - "-Zm (Compileroption) [C++]"
ms.assetid: 94c77d5e-6672-46a7-92e0-3f69e277727d
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# /Zm (Begrenzung der Speicherzuweisung f&#252;r vorkompilierten Header festlegen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt den Arbeitsspeicher, den der Compiler für die Erstellung von vorkompilierten Headern belegt.  
  
## Syntax  
  
```  
/Zmfactor  
```  
  
## Argumente  
 `factor`  
 Ein Skalierungsfaktor zur Bestimmung des Arbeitsspeichers, den der Compiler für die Erstellung vorkompilierter Header verwendet.  
  
 Das Argument `factor` ist ein Prozentsatz der Standardgröße eines vom Compiler definierten Arbeitspuffers.  Standardmäßig liegt der Wert des Arguments `factor` bei 100 \(Prozent\), Sie können diesen Wert aber erhöhen oder verringern.  
  
## Hinweise  
 In früheren Versionen von Visual C\+\+ verwendete der Compiler eine Reihe von eigenständigen Heaps, die jeweils über eine feste Begrenzung verfügten.  Derzeit werden die Heaps bei Bedarf vom Compiler dynamisch bis zu einem Grenzwert für die Heapgesamtgröße vergrößert; nur zum Erstellen vorkompilierter Header ist ein Puffer mit fester Größe erforderlich.  Infolgedessen ist die Compileroption **\/Zm** selten notwendig.  
  
 Wenn der Compiler nicht mehr über ausreichenden Heapspeicher verfügt und bei Verwendung der Compileroption **\/Zm** die Fehlermeldung [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) ausgibt, haben Sie möglicherweise zu viel Arbeitsspeicher reserviert.  Erwägen Sie, die Option **\/Zm** zu entfernen.  Wenn der Compiler die Fehlermeldung [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) ausgibt, wird in der zugehörigen Meldung [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) das Argument `factor` angegeben, das bei der erneuten Kompilierung mit der Compileroption **\/Zm** verwendet werden soll.  
  
 In der folgenden Tabelle wird dargestellt, inwiefern sich das Argument `factor` bei einer angenommenen Größe des Standardpuffers für vorkompilierte Header von 75 MB auf die maximale Speicherbelegung auswirkt.  
  
|Wert von `factor`|Maximale Speicherbelegung|  
|-----------------------|-------------------------------|  
|10|7.5 MB|  
|100|75 MB|  
|200|150 MB|  
|1000|750 MB|  
|2000|1500 MB|  
  
## Weitere Möglichkeiten zur Festlegung der maximalen Speicherbelegung  
  
#### So legen Sie die Compileroption "\/Zm" in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Wählen Sie im Navigationsbereich die Optionen **Konfigurationseigenschaften**, **C\/C\+\+**, **Befehlszeile** aus.  
  
3.  Geben Sie im Feld **Zusätzliche Optionen** die Compileroption **\/Zm** ein.  
  
#### So legen Sie die Compileroption "\/Zm" programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
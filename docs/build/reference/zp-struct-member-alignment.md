---
title: "/Zp (Ausrichten des Strukturmembers) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/zp"
  - "VC.Project.VCCLCompilerTool.StructMemberAlignment"
  - "VC.Project.VCCLWCECompilerTool.StructMemberAlignment"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zp (Compileroption) [C++]"
  - "Ausrichten des Strukturmembers (Compileroption)"
  - "Zp (Compileroption)"
  - "-Zp (Compileroption) [C++]"
ms.assetid: 5242f656-ed9b-48a3-bc73-cfcf3ed2520f
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /Zp (Ausrichten des Strukturmembers)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit dieser Option wird gesteuert, wie die Member einer Struktur im Speicher ausgerichtet werden. Außerdem wird damit festgelegt, dass alle Strukturen in einem Modul auf gleiche Weise ausgerichtet werden.  
  
## Syntax  
  
```  
/Zp[1|2|4|8|16]  
```  
  
## Hinweise  
 Wenn Sie diese Option angeben, wird jeder Strukturmember nach dem ersten entweder in der Größe des Membertyps oder innerhalb der Grenzen von `n` Bytes \(wobei `n` den Wert 1, 2, 4, 8 oder 16 haben kann\) gespeichert, je nachdem, was kleiner ist.  
  
 Die verfügbaren Werte sind in der folgenden Tabelle beschrieben.  
  
 1  
 Komprimiert Strukturen auf 1\-Byte\-Begrenzungen.  Dieselbe Bedeutung wie **\/Zp**.  
  
 2  
 Komprimiert Strukturen auf 2\-Byte\-Begrenzungen.  
  
 4  
 Komprimiert Strukturen auf 4\-Byte\-Begrenzungen.  
  
 8  
 Komprimiert Strukturen auf 8\-Byte\-Begrenzungen \(Standard\).  
  
 16  
 Komprimiert Strukturen auf 16\-Byte\-Begrenzungen.  
  
 Sie sollten diese Option nur dann verwenden, wenn Sie besondere Anforderungen an die Ausrichtung haben.  
  
 Sie können das Ausrichten von Strukturen auch mit [pack](../../preprocessor/pack.md) steuern.  Weitere Informationen zur Ausrichtung finden Sie unter:  
  
-   [align](../../cpp/align-cpp.md)  
  
-   [\_\_alignof\-Operator](../../cpp/alignof-operator.md)  
  
-   [\_\_unaligned](../../cpp/unaligned.md)  
  
-   [Beispiele für die Strukturausrichtung](../../build/examples-of-structure-alignment.md) \(x64\-spezifisch\)  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Codegenerierung**.  
  
4.  Ändern Sie die Eigenschaft **Ausrichten des Strukturmitglieds**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
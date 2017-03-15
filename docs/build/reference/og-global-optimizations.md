---
title: "/Og (Globale Optimierungen) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.GlobalOptimizations"
  - "/og"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Og (Compileroption) [C++]"
  - "Automatische Registerreservierung"
  - "Gemeinsame Teilausdrücke entfernen"
  - "Globale Optimierung (Compileroption) [C++]"
  - "Schleifenstruktur, Optimieren"
  - "Og (Compileroption) [C++]"
  - "-Og (Compileroption) [C++]"
ms.assetid: d10630cc-b9cf-4e97-bde3-8d7ee79e9435
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /Og (Globale Optimierungen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bietet lokale und globale Optimierungen, automatische Registerreservierung und Schleifenoptimierung.  Veraltet.  
  
## Syntax  
  
```  
/Og  
```  
  
## Hinweise  
 Die folgenden Optimierungen sind verfügbar:  
  
-   Entfernen lokaler und globaler gemeinsamer Teilausdrücke  
  
     Bei dieser Optimierung wird der Wert eines gemeinsamen Teilausdrucks nur einmal berechnet.  Wenn sich im folgenden Beispiel die Werte `b` und `c` zwischen den drei Ausdrücken nicht ändern, kann der Compiler das Ergebnis aus  `b + c` einer temporären Variablen zuweisen und `b + c`durch diese Variable ersetzen.  
  
    ```  
    a = b + c;  
    d = b + c;  
    e = b + c;  
    ```  
  
     Bei der Optimierung lokaler gemeinsamer Teilausdrücke durchsucht der Compiler kurze Codeabschnitte nach gemeinsamen Teilausdrücken.  Bei der Optimierung globaler gemeinsamer Teilausdrücke durchsucht der Compiler ganze Funktionen nach gemeinsamen Teilausdrücken.  
  
-   Automatische Registerreservierung  
  
     Diese Optimierung ermöglicht es dem Compiler, häufig verwendete Variablen und Teilausdrücke in Registern zu speichern. Das Schlüsselwort `register` wird ignoriert.  
  
-   Schleifenoptimierung  
  
     Bei dieser Optimierung werden gleichbleibende Teilausdrücke aus dem Rumpf einer Schleife entfernt.  Eine optimale Schleife enthält nur Ausdrücke, deren Wert sich bei der Ausführung der Schleife ändert.  Im folgenden Beispiel ändert sich der Ausdruck `x + y` im Schleifenrumpf nicht:  
  
    ```  
    i = -100;  
    while( i < 0 ) {  
        i += x + y;  
    }  
    ```  
  
     Nach der Optimierung wird `x + y` nur einmal berechnet, statt bei jeder Ausführung der Schleife:  
  
    ```  
    i = -100;  
    t = x + y;  
    while( i < 0 ) {  
        i += t;  
    }  
    ```  
  
     Die Schleifenoptimierung arbeitet wesentlich effektiver, wenn der Compiler davon ausgehen kann, dass kein Aliasing verwendet wird. Dies können Sie mit [\_\_restrict](../../cpp/extension-restrict.md), [noalias](../../cpp/noalias.md) oder [restrict](../../cpp/restrict.md) festlegen.  
  
    > [!NOTE]
    >  Sie können die globale Optimierung für jede Funktion aktivieren oder deaktivieren, indem Sie das `optimize` \-Pragma mit der Option `g` verwenden.  
  
 Mit **\/Og** wird außerdem die Optimierung des benannten Rückgabewerts aktiviert. Kopierkonstruktor und \-destruktor eines stapelbasierten Rückgabewerts werden dadurch eliminiert.  Weitere Informationen finden Sie unter [\/O1, \/O2 \(Größe minimieren, Geschwindigkeit maximieren\)](../../build/reference/o1-o2-minimize-size-maximize-speed.md).  
  
 Weitere Informationen finden Sie unter [Generieren systeminterner Funktionen \(\/Oi\)](../../build/reference/oi-generate-intrinsic-functions.md) und [Komplette Optimierung \(\/Ox\)](../../build/reference/ox-full-optimization.md).  
  
 **\/Og** ist veraltet. Verwenden Sie stattdessen entweder [\/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md) oder **\/O2**.  Weitere Informationen finden Sie unter [Deprecated Compiler Options in Visual C\+\+ 2005](assetId:///aa59fce3-50b8-4f66-9aeb-ce09a7a84cce).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [\/O\-Optionen \(Code optimieren\)](../../build/reference/o-options-optimize-code.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
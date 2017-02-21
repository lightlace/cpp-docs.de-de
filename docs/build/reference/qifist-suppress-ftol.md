---
title: "/QIfist (_ftol unterdr&#252;cken) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/qifist"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "QIfist (Compileroption) [C++]"
  - "-QIfist (Compileroption) [C++]"
  - "/QIfist (Compileroption) [C++]"
ms.assetid: 1afd32a5-f658-4b66-85f4-e0ce4cb955bd
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# /QIfist (_ftol unterdr&#252;cken)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unterdrückt den Aufruf der `_ftol`\-Hilfsfunktion, wenn eine Konvertierung von einem Gleitkommatyp zu einem ganzzahligen Typ erforderlich ist.  
  
## Syntax  
  
```  
/QIfist  
```  
  
## Hinweise  
  
> [!NOTE]
>  **\/QIfist** ist nur im Compiler verfügbar, der auf x86 abzielt. Diese Compileroption steht nicht in Compilern zur Verfügung, die auf [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] oder ARM abzielen.  
  
 Durch die `_ftol`\-Funktion wird nicht nur ein Gleitkommatyp in einen ganzzahligen Typ konvertiert, sondern ist auch gewährleistet, dass die Gleitkommaeinheit \(Floating\-Point Unit, FPU\) gegen 0 \(null\) rundet \(abschneidet\), indem die Bits 10 und 11 des Steuerworts entsprechend festgelegt werden.  Dadurch wird garantiert, dass die Konvertierung eines Gleitkommatyps in einen ganzzahligen Typ wie im ANSI C\-Standard durchgeführt wird, dass also der Teil nach dem Komma verworfen wird.  Wenn Sie **\/QIfist** verwenden, ist dies nicht mehr sichergestellt.  Das Rundungsverhalten entspricht einem der vier im Intel\-Referenzmaterial dokumentierten Modi:  
  
-   Runden auf die nächste Maschinenzahl \(auf eine gerade Zahl bei gleichem Abstand\)  
  
-   Runden in Richtung minus unendlich  
  
-   Runden in Richtung plus unendlich  
  
-   Runden in Richtung Null \(0\)  
  
 Mit der [\_control87, \_controlfp, \_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)\-C\-Laufzeitfunktion können Sie das Rundungsverhalten der FPU ändern.  Die Standardeinstellung der FPU ist "Runden auf die nächste Maschinenzahl". Mithilfe von **\/QIfist** kann die Leistung der Anwendung erhöht werden, jedoch nicht ohne Risiko.  Die Teile des Codes, bei denen Rundungsmodi eine Rolle spielen, sollten gründlich getestet werden, bevor Sie sich in einer Produktionsumgebung auf Code verlassen, der mit **\/QIfist** erstellt wurde.  
  
 [\/arch \(x86\)](../../build/reference/arch-x86.md) und **\/QIfist** dürfen nicht in derselben Kompiliereinheit verwendet werden.  
  
> [!NOTE]
>  In der Standardeinstellung ist **\/QIfist** deaktiviert, da die gerundeten Bits auch das Runden von Gleitkomma auf Gleitkomma \(das in jeder Berechnung auftritt\) betreffen. Wenn Sie daher die Flags auf das Runden im C\-Format \(gegen Null\) festlegen, führen die Gleitkommaberechnungen unter Umständen zu einem anderen Ergebnis.  **\/QIfist** sollte nicht verwendet werden, wenn der Code auf der erwarteten Kürzung des Bruchteils der Gleitkommazahl aufbaut.  Verwenden Sie **\/QIfist** im Zweifelsfall nicht.  
  
 **\/QIfist** ist veraltet.  Für den Compiler wurde die Geschwindigkeit der Konvertierung von Gleitkommatyp in ganzzahligen Typ deutlich erhöht.  Weitere Informationen finden Sie unter [Deprecated Compiler Options in Visual C\+\+ 2005](assetId:///aa59fce3-50b8-4f66-9aeb-ce09a7a84cce).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [\/Q\-Optionen \(Operationen auf niedriger Ebene\)](../../build/reference/q-options-low-level-operations.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
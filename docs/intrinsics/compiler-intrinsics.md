---
title: "Intrinsische Compilerfunktionen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe-Compiler, Interna"
  - "cl.exe-Compiler, Leistung"
  - "Intrinsische Compilerfunktionen"
  - "Interna, Compiler"
ms.assetid: 48bb9929-7d78-4fd8-a092-ae3c9f971858
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# Intrinsische Compilerfunktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die meisten Funktionen sind in Bibliotheken enthalten, aber einige Funktionen sind in den Compiler integriert \(das heißt, sie sind systemintern\).  Diese werden als systeminterne Funktionen bezeichnet.  
  
## Hinweise  
 Wenn eine Funktion systemintern ist, wird der Code für diese Funktion normalerweise inline eingefügt, damit wird der Mehraufwand eines Funktionsaufrufs vermieden und es können äußerst effiziente Computerbefehle für diese Funktion ausgegeben werden.  Eine systeminterne Funktion ist häufig schneller als die entsprechende Inlineassembly, da der Optimierer über integriertes Wissen über das Verhalten vieler systeminterner Funktionen verfügt, sodass einige Optimierungen verfügbar sein können, die bei Verwendung von Inlineassemblys nicht verfügbar sind.  Außerdem kann der Optimierer die systeminterne Funktion anders erweitern, Puffer anders ausrichten oder je nach Kontext und den Argumenten des Aufrufs andere Anpassungen vornehmen.  
  
 Die Verwendung systeminterner Funktionen beeinflusst die Portabilität des Codes, da die in Visual C\+\+ verfügbaren systeminternen Funktionen möglicherweise nicht zur Verfügung stehen, wenn der Code mit anderen Compilern und einigen systeminternen Funktionen kompiliert wird, die möglicherweise für einige aber nicht für alle Zielarchitekturen verfügbar sind.  Allerdings sind systeminterne Funktionen in der Regel besser portierbar als Inlineassemblys.  Systeminternen Funktionen sind auf 64\-Bit\-Architekturen erforderlich, auf denen Inlineassemblys nicht unterstützt werden.  
  
 Einige systeminterne Funktionen, wie `__assume` und `__ReadWriteBarrier`, stellen dem Compiler Informationen bereit, die das Verhalten des Optimierers beeinflussen.  
  
 Einige systeminterne Funktionen sind nur als systeminterne Funktionen verfügbar, und einige sind sowohl in Funktionsimplementierungen als auch in systeminternen Implementierungen verfügbar.  Sie können den Compiler anweisen, die systeminterne Implementierung auf einer von zwei Arten zu verwenden, je nach dem, ob Sie nur bestimmte Funktionen aktivieren möchten, oder ob Sie alle systeminternen Funktionen aktivieren möchten.  Die erste Verwendungsart ist: `#pragma intrinsic(``intrinsic-function-name-list``)`.  Das Pragma kann verwendet werden, um eine einzelne systeminterne Funktion oder mehrere durch Trennzeichen getrennte systeminterne Funktionen angeben.  Die zweite Möglichkeit ist die Verwendung der [\/Oi \(Generieren von systeminternen Funktionen\)](../build/reference/oi-generate-intrinsic-functions.md)\-Compileroption, mit der alle systeminternen Funktionen auf einer bestimmten Plattform bereitgestellt werden.  Verwenden Sie unter **\/Oi** die `#pragma function(``intrinsic-function-name-list``)`, um die Verwendung eines Funktionsaufrufs anstelle einer systeminternen Funktion zu erzwingen.  Wenn in der Dokumentation für einer bestimmte systeminterne Funktion darauf hingewiesen wird, dass eine Routine nur als systeminterne Funktion verfügbar ist, dann wird systeminterne Implementierung verwendet, unabhängig davon, ob **\/Oi** oder `#pragma intrinsic`  angegeben wird.  In allen Fällen gestattet **\/Oi** oder `#pragma intrinsic` dem Optimierer die Verwendung systeminterner Funktion. Das wird jedoch nicht erzwungen.  Die Funktion kann vom Optimierer noch immer aufgerufen werden.  
  
 Einige C bzw. C\+\+\-Standardbibliotheksfunktionen sind in den systeminternen Implementierungen einiger Architekturen verfügbar.  Wird eine CRT\-Funktion aufgerufen, wird die systeminterne Implementierung verwendet, sofern **\/Oi** in der Befehlszeile angegeben wird.  
  
 Es ist eine Headerdatei, \<intrin.h\>, vefügbar, die die Prototypen für die gängigsten systeminternen Funktionen deklariert.  Herstellerspezifische systeminterne Funktionen stehen in den Headerdateien \<immintrin.h\> und \<ammintrin.h\> zur Verfügung.  Außerdem deklarieren bestimmte Windows\-Header Funktionen, die auf eine systeminterne Compilerfunktion zuordnen.  
  
 In den folgenden Abschnitten werden alle systeminternen Funktionen aufgeführt, die auf verschiedenen Architekturen verfügbar sind.  Weitere Informationen zu der Funktionsweise systeminterner Funktionen auf dem bestimmten Zielprozessor finden Sie in der Referenzdokumentation des Herstellers.  
  
-   [Systeminterne ARM\-Funktionen](../intrinsics/arm-intrinsics.md)  
  
-   [Liste der intrinsischen Funktionen für x86](../intrinsics/x86-intrinsics-list.md)  
  
-   [Liste der intrinsischen Funktionen für x64 \(amd64\)](../intrinsics/x64-amd64-intrinsics-list.md)  
  
-   [Systeminterne Funktionen verfügbar für alle Architekturen](../intrinsics/intrinsics-available-on-all-architectures.md)  
  
-   [Alphabetische Liste von systeminternen Funktionen](../intrinsics/alphabetical-listing-of-intrinsic-functions.md)  
  
## Siehe auch  
 [ARM Assembler Reference](../assembler/arm/arm-assembler-reference.md)   
 [Microsoft Macro Assembler Reference](../assembler/masm/microsoft-macro-assembler-reference.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [C\-Laufzeitbibliotheksverweis](../c-runtime-library/c-run-time-library-reference.md)
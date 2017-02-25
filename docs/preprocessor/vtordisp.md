---
title: "vtordisp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.vtordisp"
  - "vtordisp_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Pragmas, vtordisp"
  - "vtordisp-Pragma"
ms.assetid: 05b7d73c-43fa-4b62-8c8a-170a9e427391
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# vtordisp
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+\-spezifisch**  
  
 Steuert das Hinzufügen ausgeblendeter vtordisp\-Member zur Konstruktor\-\/Destruktorverschiebung.  
  
## Syntax  
  
```cpp  
#pragma vtordisp([push,] n)  
#pragma vtordisp(pop)  
#pragma vtordisp()  
#pragma vtordisp([push,] {on | off})  
```  
  
#### Parameter  
 `push`  
 Legt die aktuelle vtordisp\-Einstellung auf dem internen Compilerstapel ab und legt die neue vtordisp\-Einstellung auf `n` fest.  Wenn `n` nicht angegeben ist, wird die aktuelle vtordisp\-Einstellung nicht geändert.  
  
 `pop`  
 Entfernt den obersten Datensatz aus dem internen Compilerstapel und setzt die vtordisp\-Einstellung auf den entfernten Wert zurück.  
  
 `n`  
 Gibt den neuen Wert für die vtordisp\-Einstellung an.  Mögliche Werte sind 0, 1 oder 2, entsprechend den \/vd0\-, \/vd1\- und \/vd2\- Compileroptionen.  Weitere Informationen finden Sie unter [\/vd \(Konstruktionsverschiebungen deaktivieren\)](../build/reference/vd-disable-construction-displacements.md).  
  
 `on`  
 Entspricht `#pragma vtordisp(1)`.  
  
 `off`  
 Entspricht `#pragma vtordisp(0)`.  
  
## Hinweise  
 Das Pragma `vtordisp` ist nur auf Code anwendbar, der virtuelle Basen verwendet.  Wenn eine abgeleitete Klasse eine virtuelle Funktion überschreibt, die sie von einer virtuellen Basisklasse erbt, und wenn ein Konstruktor oder Destruktor der abgeleiteten Klasse die Funktion mithilfe eines Zeigers auf die virtuelle Basisklasse aufruft, kann der Compiler zusätzliche ausgeblendete `vtordisp`\-Felder in die Klassen mit virtuellen Basen einführen.  
  
 Das Pragma `vtordisp` wirkt sich auf das Layout der Klassen, die darauf folgen, aus.  Die \/vd0\-, \/vd1\- und \/vd2\-Optionen geben dasselbe Verhalten für vollständige Module an.  Durch das Angeben von `0` bzw. `off` werden die ausgeblendeten `vtordisp`\-Member unterdrückt.  Deaktivieren Sie `vtordisp` nur dann, wenn keine Möglichkeit besteht, dass die Konstruktoren und Destruktoren der Klasse virtuelle Funktionen für das Objekt aufrufen, auf das der `this`\-Zeiger zeigt.  
  
 Durch das Angeben von `1` oder `on`, dem Standard, werden die ausgeblendeten `vtordisp`\-Member aktiviert, wo sie notwendig sind.  
  
 Durch das Angeben von `2` werden die ausgeblendeten `vtordisp`\-Member für alle virtuellen Basen mit virtuellen Funktionen aktiviert. `vtordisp(2)` kann notwendig sein, um eine korrekte Leistung von `dynamic_cast` auf einem teilweise konstruierten Objekt sicherzustellen.  Weitere Informationen finden Sie unter [Compilerwarnung \(Stufe 1\) C4436](../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md).  
  
 `#pragma vtordisp()`, ohne Argumente, setzt die vtordisp\-Einstellung auf die ursprüngliche Einstellung zurück.  
  
```  
#pragma vtordisp(push, 2)  
class GetReal : virtual public VBase { ... };  
#pragma vtordisp(pop)  
```  
  
 **Ende C\+\+\-spezifisch**  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
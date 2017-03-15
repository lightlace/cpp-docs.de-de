---
title: "conform | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "conform_CPP"
  - "vc-pragma.conform"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conform-Pragma"
  - "forScope conform-Pragma"
  - "Pragmas, conform"
ms.assetid: 71b3e174-c53c-4bfc-adf3-af39b1554191
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# conform
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+\-spezifisch**  
  
 Gibt das Laufzeitverhalten für die [\/Zc:forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)\-Compileroption an.  
  
## Syntax  
  
```  
#pragma conform(name [, show ] [, on | off ] [ [, push | pop ] [, identifier ] ] )  
```  
  
#### Parameter  
 *name*  
 Gibt den Namen der zu ändernden Compileroption an.  Der einzige gültige *Name* ist `forScope`.  
  
 **show** \(optional\)  
 Bewirkt, dass die aktuelle Einstellung von *name* \("true" oder "false"\) während der Kompilierung mittels einer Warnmeldung angezeigt wird.  Beispielsweise `#pragma conform(forScope, show)`.  
  
 **on, off** \(optional\)  
 Das Festlegen von *name* auf **on** aktiviert die [\/Zc:forScope](../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)\-Compileroption.  Der Standardwert ist **off**.  
  
 **push** \(optional\)  
 Legt den aktuellen Wert von *name* auf dem internen Compilerstapel ab.  Wenn Sie *identifier* verwenden, können Sie den **on**\- oder **off**\-Wert für *name* angeben, der auf dem Stapel abgelegt wird.  Beispielsweise `#pragma conform(forScope, push, myname, on)`.  
  
 **pop** \(optional\)  
 Legt den Wert von *name* auf den Wert an oberster Position des internen Compilerstapels fest und ruft dann den Stapel ab.  Wenn der Bezeichner mit **pop** angegeben ist, wird der Stapel reduziert, bis der Datensatz mit *identifier* gefunden wird, der auch vom Stapel entfernt wird. Der aktuelle Wert für *name* im nächsten Datensatz auf dem Stapel wird der neue Wert für *name*.  Wenn Sie ein Element vom Stapel mit einem *identifier* entfernen möchten, der nicht in einem Datensatz im Stapel ist, wird **pop** ignoriert.  
  
 *identifier* \(optional\)  
 Kann in einem **push**\- oder **pop**\-Befehl hinzugefügt werden.  Wenn *identifier* genutzt wird, kann auch einer der **on**\- oder **off**\-Spezifizierer verwendet werden.  
  
## Beispiel  
  
```  
// pragma_directive_conform.cpp  
// compile with: /W1  
// C4811 expected  
#pragma conform(forScope, show)  
#pragma conform(forScope, push, x, on)  
#pragma conform(forScope, push, x1, off)  
#pragma conform(forScope, push, x2, off)  
#pragma conform(forScope, push, x3, off)  
#pragma conform(forScope, show)  
#pragma conform(forScope, pop, x1)  
#pragma conform(forScope, show)  
  
int main() {}  
```  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
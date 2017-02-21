---
title: "Kommaoperator: , | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "%2C"
  - ","
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Kommaoperator"
ms.assetid: 38e0238e-19da-42ba-ae62-277bfdab6090
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Kommaoperator: ,
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ermöglicht das Gruppieren von zwei Anweisungen, wo eine erwartet wird.  
  
## Syntax  
  
```  
  
expression , expression  
```  
  
## Hinweise  
 Der Operator Komma weist eine Assoziativität von links nach rechts auf.  Zwei Ausdrücke, die durch ein Komma getrennt werden, werden von links nach rechts ausgewertet.  Der linke Operand wird immer ausgewertet und alle Nebeneffekte werden abgeschlossen, bevor der rechte Operand ausgewertet wird.  
  
 Kommas können in einigen Kontexten, z. B. Funktionsargumentlisten, als Trennzeichen verwendet werden.  Verwechseln Sie die Verwendung des Kommas als Trennzeichen nicht mit seiner Verwendung als Operator. Die beiden Anwendungsmöglichkeiten sind vollkommen unterschiedlich.  
  
 Betrachten Sie den Ausdruck  
  
 *e1* , *e2*  
  
 Typ und Wert des Ausdrucks entsprechen Typ und Wert von *e2*. Das Ergebnis der Auswertung von *e1* wird verworfen.  Dieses Ergebnis ist ein l\-Wert, wenn der rechte Operand ein l\-Wert ist.  
  
 Während das Komma normalerweise als Trennzeichen verwendet wird \(z. B. in tatsächlichen Argumenten für Funktionen oder Aggregatinitialisierer\), müssen der Komma\-Operator und seine Operanden in Klammern eingeschlossen werden.  Beispiel:  
  
```  
func_one( x, y + 2, z );  
func_two( (x--, y + 2), z );  
```  
  
 Im obigen Funktionsaufruf an `func_one` werden drei durch Trennzeichen getrennte Argumente übergeben: `x`, `y + 2` und `z`.  Im Funktionsaufruf an `func_two` zwingen Klammern den Compiler, das erste Komma als Operator für sequenzielle Auswertung zu interpretieren.  Dieser Funktionsaufruf übergibt zwei Argumente an `func_two`.  Das erste Argument ist das Ergebnis der Sequentialauswertungsoperation `(x--, y + 2)`, welche den Wert und den Typ des Ausdrucks `y + 2` hat; das zweite Argument ist `z`.  
  
## Beispiel  
  
```  
// cpp_comma_operator.cpp  
#include <stdio.h>  
int main () {  
   int i = 10, b = 20, c= 30;  
   i = b, c;  
   printf("%i\n", i);  
  
   i = (b, c);  
   printf("%i\n", i);  
}  
```  
  
  **20**  
**30**   
## Siehe auch  
 [Ausdrücke mit binären Operatoren](../cpp/expressions-with-binary-operators.md)   
 [C\+\+\-Operatoren](../misc/cpp-operators.md)   
 [C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Operator für sequenzielle Auswertungen](../c-language/sequential-evaluation-operator.md)
---
title: "Compilerwarnung (Stufe 4) C4754"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4754"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4754"
ms.assetid: e0e4606a-754a-4f42-a274-21a34978d21d
caps.latest.revision: 6
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4754
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Aufgrund von Konvertierungsregeln für arithmetische Operationen in einem Vergleich kann eine Verzweigung nicht ausgeführt werden.  
  
 Die Warnung C4754 wird ausgegeben, da das Ergebnis des Vergleichs immer identisch ist.  Dies bedeutet, dass eine der Verzweigungen der Bedingung nie ausgeführt wird, weil höchstwahrscheinlich der zugehörige ganzzahligen Ausdruck falsch ist.  Dieser Fehler tritt häufig in falschen Ganzzahl\-Überlaufüberprüfungen in 64\-Bit\-Architekturen auf.  
  
 Konvertierungsregeln für Ganzzahlen sind komplex und enthalten viele subtile Fehlermöglichkeiten.  Statt die Ursache jeder C4754\-Warnung zu beheben, können Sie den Code so aktualisieren, dass er die [SafeInt\-Bibliothek](../../windows/safeint-library.md) verwendet.  
  
## Beispiel  
 Dieses Beispiel generiert C4754:  
  
```cpp  
// C4754a.cpp  
// Compile with: /W4 /c  
#include "errno.h"  
  
int sum_overflow(unsigned long a, unsigned long b)   
{  
   unsigned long long x = a + b; // C4754  
  
   if (x > 0xFFFFFFFF)   
   {  
      // never executes!  
      return EOVERFLOW;  
   }  
   return 0;  
}  
```  
  
 Die Addition `a + b` kann einen arithmetischen Überlauf verursachen, bevor das Ergebnis in einen 64\-Bit\-Wert umgewandelt und der 64\-Bit\-Variablen `x` zugewiesen wird.  Dies bedeutet, dass die Überprüfung für `x` redundant ist und nie einen Überlauf abgefangen wird.  In diesem Fall gibt der Compiler folgende Warnung aus:  
  
  **Warnung C4754: Aufgrund von Konvertierungsregeln für arithmetische Operationen im Vergleich in C4754a.cpp \(7\) kann eine Verzweigung nicht ausgeführt werden.  Wandeln Sie '\(a \+ ...\)' in 'ULONG64' um \(oder in einen ähnlichen Typ mit 8 Bytes\).**  Um die Warnung zu vermeiden, können Sie die Zuweisungsanweisung so ändern, dass die Operanden in 8\-Byte\-Werten umgewandelt werden:  
  
```cpp  
// Casting one operand is sufficient to force all the operands in   
// the addition be upcast according to C/C++ conversion rules, but  
// casting both is clearer.  
unsigned long long x =   
   (unsigned long long)a + (unsigned long long)b;  
```  
  
## Beispiel  
 Im nächsten Beispiel wird ebenfalls C4754 generiert.  
  
```cpp  
// C4754b.cpp  
// Compile with: /W4 /c  
#include "errno.h"  
  
int wrap_overflow(unsigned long a)   
{  
   if (a + sizeof(unsigned long) < a) // C4754  
   {   
      // never executes!  
      return EOVERFLOW;  
   }  
   return 0;  
}  
```  
  
 Der Operator `sizeof()` gibt `size_t` zurück, dessen Größe architekturabhängig ist.  Der Beispielcode funktioniert mit 32\-Bit\-Architekturen, da `size_t` dort ein 32\-Bit\-Typ ist.  In 64\-Bit\-Architekturen ist `size_t` jedoch ein 64\-Bit\-Typ.  Aufgrund der Konvertierungsregeln für ganze Zahlen wird `a` im Ausdruck `a + b < a` in einen 64\-Bit\-Wert umgewandelt ist, so als ob der Ausdruck `(size_t)a + (size_t)b < (size_t)a` lauten würde.  Wenn `a` und `b` ganze 32\-Bit\-Zahlen sind, kann die 64\-Bit\-Addition nie überlaufen, und die Zwangsbedingung trifft nie zu.  Daher erkennt der Code in 64\-Bit\-Architekturen nie eine Ganzzahlüberlaufbedingung.  In diesem Beispiel gibt der Compiler folgende Warnung aus:  
  
  **Warnung C4754: Aufgrund von Konvertierungsregeln für arithmetische Operationen im Vergleich in C4754b.cpp \(7\) kann eine Verzweigung nicht ausgeführt werden.  Wandeln Sie '4' in 'ULONG' um \(oder in einen ähnlichen Typ mit 4 Bytes\)**  Beachten Sie, dass die Warnmeldung explizit den konstanten Wert 4 statt der ursprünglichen Quellzeichenfolge angibt, da `sizeof(unsigned long)` zu dem Zeitpunkt, an dem die Warnungsanalyse auf den fehlerhaften Code trifft, bereits in eine Konstante konvertiert wurde.  Daher müssen Sie ermitteln, welcher Ausdruck im Quellcode dem konstanten Wert in der Warnmeldung zugeordnet ist.  Die häufigsten Quellen für Umwandlungen in Konstanten in C4754\-Warnmeldungen sind Ausdrücke wie `sizeof(TYPE)` und `strlen(szConstantString)`.  
  
 In diesem Fall würde der geänderte Code dem Folgenden ähneln:  
  
```cpp  
// Casting the result of sizeof() to unsigned long ensures  
// that all the addition operands are 32-bit, so any overflow   
// is detected by the check.  
if (a + (unsigned long)sizeof(unsigned long) < a)  
  
```  
  
 **Hinweis** Die Zeilennummer, auf die in Compilerwarnungen verwiesen wird, ist die letzte Zeile eine Anweisung.  In einer Warnmeldung zu einer komplexen Bedingungsanweisung, die sich über mehrere Zeilen erstreckt, kann die Zeile mit dem Codefehler einige Zeilen vor der Zeile liegen, die gemeldet wird.  Beispiel:  
  
```cpp  
unsigned long a;  
  
if (a + sizeof(unsigned long) < a || // incorrect check  
    condition1() ||   
    a == 0) {    // C4754 warning reported on this line  
         // never executes!  
         return INVALID_PARAMETER;  
}  
  
```
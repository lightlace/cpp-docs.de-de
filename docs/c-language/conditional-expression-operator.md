---
title: "Bedingter Ausdrucksoperator | Microsoft Docs"
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
  - "Bedingte Operatoren"
  - "Ausdrücke [C++], Bedingt"
  - "Operatoren [C++], Bedingt"
ms.assetid: c4f1a5ca-0844-44a7-a384-eca584d4e3dd
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Bedingter Ausdrucksoperator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C hat einen ternären Operator: den bedingten Ausdrucksoperator \(**? :**\).  
  
## Syntax  
 *Bedingter Ausdruck*:  
 *Ausdruck für 'logisches OR'*  
  
 *Ausdruck für 'logisches OR'*  **?**  *Ausdruck*  **:**  *Bedingter Ausdruck*  
  
 Der *Ausdruck für 'logisches OR'* muss über Ganzzahl\-, Gleitkomma\- oder Zeigertypen verfügen.  Er wird hinsichtlich seiner Übereinstimmung mit 0 ausgewertet.  Ein Sequenzpunkt folgt dem *Ausdruck für 'logisches OR'*.  Die Auswertung der Operanden wird wie folgt ausgeführt:  
  
-   Wenn der *Ausdruck für 'logisches OR'* ungleich 0 ist, wird der *Ausdruck* ausgewertet.  Das Ergebnis der Auswertung des Ausdrucks wird durch den Nichtterminal\- *Ausdruck* angegeben. \(Dies bedeutet, dass der *Ausdruck* nur ausgewertet wird, wenn der *Ausdruck für 'logisches OR'* "true" ist.\)  
  
-   Wenn *Ausdruck für 'logisches OR'* gleich 0 ist, wird der *bedingte Ausdruck* ausgewertet.  Das Ergebnis des Ausdrucks ist der Wert des *bedingten Ausdrucks*. \(Dies bedeutet, dass der *bedingte Ausdruck* nur ausgewertet wird, wenn der *Ausdruck für 'logisches OR'* "false" ist.\)  
  
 Es wird entweder nur der *Ausdruck* oder der *bedingte Ausdruck* ausgewertet, jedoch nicht beide.  
  
 Der Typ des Ergebnisses einer bedingten Operation hängt wie folgt vom Typ des *Ausdrucks* oder des *bedingten Ausdrucksoperanden* ab:  
  
-   Wenn der *Ausdruck* oder der *bedingte Ausdruck* über einen Ganzzahl\- oder Gleitkommatyp verfügt \(ihre Typen können unterschiedlich sein\), führt der Operator die üblichen arithmetischen Konvertierungen aus.  Der Ergebnistyp ist der Typ der Operanden nach der Konvertierung.  
  
-   Wenn sowohl der *Ausdruck* als auch der *bedingte Ausdruck* denselben Struktur\-, Union\- oder Zeigertyp aufweisen, ist der Typ des Ergebnisses derselbe Struktur\-, Union\- oder Zeigertyp.  
  
-   Wenn beide Operanden den Typ `void` haben, hat das Ergebnis den Typ `void`.  
  
-   Wenn einer der Operanden ein Zeiger auf ein Objekt eines beliebigen Typs und der andere Operand ein Zeiger auf `void` ist, wird der Zeiger auf das Objekt in einen Zeiger auf einen `void` konvertiert, und das Ergebnis ist ein Zeiger auf `void`.  
  
-   Wenn einer der *Ausdrücke* oder *bedingten Ausdrücke* ein Zeiger und der andere Operand ein konstanter Ausdruck mit dem Wert 0 ist, ist der Typ des Ergebnisses der Zeigertyp.  
  
 Im Typvergleich für Zeiger sind alle Typqualifizierer \(**const** oder `volatile`\) in dem Typ, auf den der Zeiger weist, nicht signifikant. Der Ergebnistyp erbt jedoch die Qualifizierer von beiden Komponenten des bedingten Operators.  
  
## Beispiele  
 In den folgenden Beispielen werden verschiedene Verwendungen des bedingten Operators veranschaulicht:  
  
```  
j = ( i < 0 ) ? ( -i ) : ( i );  
```  
  
 In diesem Beispiel wird der absolute Wert von `i` dem Wert `j` zugewiesen.  Wenn `i` kleiner als 0 ist, wird `-i` dem Wert `j` zugewiesen.  Wenn `i` größer oder gleich 0 ist, wird `i` dem Wert `j` zugewiesen.  
  
```  
void f1( void );  
void f2( void );  
int x;  
int y;  
    .  
    .  
    .  
( x == y ) ? ( f1() ) : ( f2() );  
```  
  
 In diesem Beispiel werden die zwei Funktionen `f1` und `f2` sowie die zwei Variablen `x` und `y` deklariert.  Wenn die zwei Variablen später im Programm den gleichen Wert haben, wird die `f1`\-Funktion aufgerufen.  Andernfalls wird `f2` aufgerufen.  
  
## Siehe auch  
 [Bedingter Operator: ? :](../cpp/conditional-operator-q.md)
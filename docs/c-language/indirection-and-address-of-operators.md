---
title: "Dereferenzierungs- und address-of-Operatoren"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "&-Operator, address-of-Operator"
  - "*-Operator"
  - "*-Operator, address-of-Operator"
  - "*-Operator, Dereferenzierungsoperator"
  - "Adressen [C++]"
  - "Adressen [C++], Dereferenzierung"
  - "address-of-Operator (&)"
  - "Und-Operator (&)"
  - "Dereferenzierungsoperator"
  - "NULL-Zeiger [C++]"
  - "Operatoren [C++], address-of"
  - "Operatoren [C++], Dereferenzierung"
ms.assetid: 10d62b00-12ba-4ea9-a2d5-09ac29ca2232
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Dereferenzierungs- und address-of-Operatoren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Indirektionsoperator \(**\***\) greift indirekt über einen Zeiger auf einen Wert zu.  Der Operand muss ein Zeigerwert sein.  Das Ergebnis des Vorgangs ist der Wert, der vom Operanden adressiert wird, also der Wert bei der Adresse, auf die der Operand zeigt.  Der Typ, den der Operand adressiert, ist der Ergebnistyp.  
  
 Wenn der Operand auf eine Funktion verweist, ist das Ergebnis ein Funktionsbezeichner.  Wenn an einen Speicherort verwiesen wird, ist das Ergebnis ein l\-Wert, der den Speicherort festlegt.  
  
 Wenn der Zeigerwert ungültig ist, ist das Ergebnis nicht definiert.  Die folgende Liste umfasst einige der häufigsten Bedingungen, die einen Zeigerwert ungültig machen.  
  
-   Der Zeiger ist ein NULL\-Zeiger.  
  
-   Der Zeiger gibt die Adresse eines lokalen Elements an, das zum Zeitpunkt des Verweises nicht sichtbar ist.  
  
-   Der Zeiger gibt eine Adresse an, die nicht ordnungsgemäß auf den Objekttyp, auf den gezeigt wird, ausgerichtet ist.  
  
-   Der Zeiger gibt eine Adresse an, die nicht vom ausgeführten Programm verwendet wird.  
  
 Der address\-of\-Operator \(**&**\) liefert die Adresse seines Operanden.  Bei dem Operand des address\-of\-Operators kann es sich entweder um einen Funktionsbezeichner oder einen l\-Wert handeln, der ein Objekt festgelegt, das kein Bitfeld ist und nicht mit dem **register**\-Speicherklassenspezifizierer deklariert wurde.  
  
 Das Ergebnis des Adressenvorgangs ist ein Zeiger auf den Operanden.  Der Typ, der vom Zeiger adressiert wird, ist der Typ des Operanden.  
  
 Der address\-of\-Operator kann nur auf Variablen vom Typ "Basis", "Struktur" oder "Union" angewendet werden, die auf Dateibereichsebene deklariert wurden, oder auf indizierte Arrayverweise.  In diesen Ausdrücken kann ein konstanter Ausdruck, der nicht den address\-of\-Operator einschließt, dem Adressausdruck hinzugefügt oder von diesem subtrahiert werden.  
  
## Beispiele  
 Im folgenden Beispiel werden diese Deklarationen verwendet:  
  
```  
int *pa, x;  
int a[20];  
double d;  
```  
  
 Diese Anweisung verwendet den address\-of\-Operator:  
  
```  
pa = &a[5];  
```  
  
 Der address\-of\-Operator \(**&**\) verwendet die Adresse des sechsten Elements des `a`\-Arrays.  Das Ergebnis wird in der Zeigervariable `pa` gespeichert.  
  
```  
x = *pa;  
```  
  
 Der Dereferenzierungsoperator \(**\***\) wird in diesem Beispiel verwendet, um auf den Wert `int` in der Adresse, die in `pa` gespeichert ist, zuzugreifen.  Der Wert wird der ganzzahligen `x`\-Variable zugewiesen.  
  
```  
if( x == *&x )  
    printf( "True\n" );  
```  
  
 In diesem Beispiel wird das Wort `True` ausgegeben. Dies zeigt, dass das Ergebnis der Anwendung des Dereferenzierungsoperators auf die Adresse von `x` dasselbe wie bei `x` ist.  
  
```  
int roundup( void );     /* Function declaration */  
  
int  *proundup  = roundup;  
int  *pround  = &roundup;  
```  
  
 Sobald die Funktion `roundup` deklariert ist, werden zwei Zeiger auf `roundup` deklariert und initialisiert.  Der erste Zeiger `proundup` wird unter ausschließlicher Verwendung des Namens der Funktion initialisiert, während der zweite Zeiger `pround` den address\-of\-Operator bei der Initialisierung verwendet.  Die Initialisierungen entsprechen sich.  
  
## Siehe auch  
 [Dereferenzierungsoperator: \*](../cpp/indirection-operator-star.md)   
 [Address\-of\-Operator: &](../cpp/address-of-operator-amp.md)
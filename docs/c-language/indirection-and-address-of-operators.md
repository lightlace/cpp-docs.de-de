---
title: Dereferenzierungs- und Address-of-Operatoren | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- address-of operator (&)
- '* operator'
- operators [C++], address-of
- ampersand operator (&)
- '* operator, indirection operator'
- addresses [C++], indirection
- addresses [C++]
- indirection operator
- '& operator, address-of operator'
- null pointers [C++]
- '* operator, address-of operator'
- operators [C++], indirection
ms.assetid: 10d62b00-12ba-4ea9-a2d5-09ac29ca2232
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 85d2510658bdf534f25ccc3efc29c88da1c93eff
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="indirection-and-address-of-operators"></a>Dereferenzierungs- und Address-of-Operatoren
Der Dereferenzierungsoperator (**\***) greift indirekt über einen Zeiger auf einen Wert zu. Der Operand muss ein Zeigerwert sein. Das Ergebnis des Vorgangs ist der Wert, der vom Operanden adressiert wird, also der Wert bei der Adresse, auf die der Operand zeigt. Der Typ, den der Operand adressiert, ist der Ergebnistyp.  
  
 Wenn der Operand auf eine Funktion verweist, ist das Ergebnis ein Funktionsbezeichner. Wenn an einen Speicherort verwiesen wird, ist das Ergebnis ein l-Wert, der den Speicherort festlegt.  
  
 Wenn der Zeigerwert ungültig ist, ist das Ergebnis nicht definiert. Die folgende Liste umfasst einige der häufigsten Bedingungen, die einen Zeigerwert ungültig machen.  
  
-   Der Zeiger ist ein NULL-Zeiger.  
  
-   Der Zeiger gibt die Adresse eines lokalen Elements an, das zum Zeitpunkt des Verweises nicht sichtbar ist.  
  
-   Der Zeiger gibt eine Adresse an, die nicht ordnungsgemäß auf den Objekttyp, auf den gezeigt wird, ausgerichtet ist.  
  
-   Der Zeiger gibt eine Adresse an, die nicht vom ausgeführten Programm verwendet wird.  
  
 Der address-of-Operator (**&**) liefert die Adresse seines Operanden. Bei dem Operanden des address-of-Operators kann es sich entweder um einen Funktionsbezeichner oder einen L-Wert handeln, der ein Objekt festgelegt, das kein Bitfeld ist und nicht mit dem **register**-Speicherklassenspezifizierer deklariert wurde.  
  
 Das Ergebnis des Adressenvorgangs ist ein Zeiger auf den Operanden. Der Typ, der vom Zeiger adressiert wird, ist der Typ des Operanden.  
  
 Der address-of-Operator kann nur auf Variablen vom Typ "Basis", "Struktur" oder "Union" angewendet werden, die auf Dateibereichsebene deklariert wurden, oder auf indizierte Arrayverweise. In diesen Ausdrücken kann ein konstanter Ausdruck, der nicht den address-of-Operator einschließt, dem Adressausdruck hinzugefügt oder von diesem subtrahiert werden.  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel werden diese Deklarationen verwendet:  
  
```  
int *pa, x;  
int a[20];  
double d;  
```  
  
 Diese Anweisung verwendet den address-of-Operator:  
  
```  
pa = &a[5];  
```  
  
 Der address-of-Operator (**&**) verwendet die Adresse des sechsten Elements des `a`-Arrays. Das Ergebnis wird in der Zeigervariable `pa` gespeichert.  
  
```  
x = *pa;  
```  
  
 Der Dereferenzierungsoperator (**\***) wird in diesem Beispiel verwendet, um auf den Wert `int` in der Adresse, die in `pa` gespeichert ist, zuzugreifen. Der Wert wird der ganzzahligen `x`-Variable zugewiesen.  
  
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
  
 Sobald die Funktion `roundup` deklariert ist, werden zwei Zeiger auf `roundup` deklariert und initialisiert. Der erste Zeiger `proundup` wird unter ausschließlicher Verwendung des Namens der Funktion initialisiert, während der zweite Zeiger `pround` den address-of-Operator bei der Initialisierung verwendet. Die Initialisierungen entsprechen sich.  
  
## <a name="see-also"></a>Siehe auch  
 [Dereferenzierungsoperator: *](../cpp/indirection-operator-star.md)   
 [address-of-Operator](../cpp/address-of-operator-amp.md)
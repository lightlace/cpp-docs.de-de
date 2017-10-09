---
title: "Speicherklassenspezifizierer „extern“ | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- extern keyword [C]
- storage class specifiers, extern
- extern keyword [C], storage class specifier
- external linkage, storage-class specifiers
- external linkage, extern modifier
ms.assetid: 6e16d927-291f-49e4-986c-9d91a482a441
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 0f11789f985c67b59b076bed7ec849a864688743
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="extern-storage-class-specifier"></a>Speicherklassenspezifizierer "extern"
Eine Variable, die mit dem `extern`-Speicherklassenspezifizierer deklariert wird, ist ein Verweis auf eine Variable mit demselben Namen, der auf der externen Ebene in einer der Quelldateien des Programms definiert ist. Die interne `extern`-Deklaration wird verwendet, um die Definition der Variablen auf externer Ebene innerhalb des Blocks sichtbar zu machen. Sofern nicht auf der externen Ebene anders deklariert, ist eine Variable, die mit dem `extern`-Schlüsselwort deklariert ist, nur in dem Block sichtbar, in dem sie deklariert ist.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel veranschaulicht Deklarationen auf interner und externer Ebene:  
  
```  
// extern_StorageClassSpecified.c  
#include <stdio.h>  
  
void other( void );  
  
int main()  
{  
    // Reference to i, defined below:   
    extern int i;  
  
    // Initial value is zero; a is visible only within main:   
    static int a;  
  
    // b is stored in a register, if possible:   
    register int b = 0;  
  
    // Default storage class is auto:   
    int c = 0;  
  
    // Values printed are 1, 0, 0, 0:   
    printf_s( "%d\n%d\n%d\n%d\n", i, a, b, c );  
    other();  
    return;  
}  
  
int i = 1;  
  
void other( void )  
{  
    // Address of global i assigned to pointer variable:  
    static int *external_i = &i;  
  
    // i is redefined; global i no longer visible:   
    int i = 16;  
  
    // This a is visible only within the other function:   
    static int a = 2;  
  
    a += 2;  
    // Values printed are 16, 4, and 1:  
    printf_s( "%d\n%d\n%d\n", i, a, *external_i );  
}  
```  
  
 In diesem Beispiel wird die Variable `i` auf der externen Ebene mit dem Anfangswert 1 definiert. Eine `extern`-Deklaration in der `main`-Funktion wird verwendet, um einen Verweis auf `i` auf der externen Ebene zu deklarieren. Die **static**-Variable `a` wird standardmäßig mit 0 initialisiert, da der Initialisierer weggelassen wird. Der Aufruf von `printf` druckt die Werte 1, 0, 0 und 0.  
  
 In der `other`-Funktion wird die Adresse der globalen Variablen `i` verwendet, um die **statische** Zeigervariable `external_i` zu initialisieren. Dies funktioniert, da die globale Variable über eine **statische** Lebensdauer verfügt. Das bedeutet, dass ihre Adresse während der Programmausführung nicht geändert wird. Danach wird die Variable `i` als lokale Variable mit dem Anfangswert 16 erneut definiert. Diese Neudefinition wirkt sich nicht auf den Wert der Variablen `i` auf der externen Ebene aus, die durch Verwendung ihres Namens für die lokale Variable verdeckt wird. Auf den Wert der globalen `i`-Variablen kann in diesem Block jetzt nur indirekt über den `external_i`-Zeiger zugegriffen werden. Der Versuch, die Adresse der **auto**-Variablen `i` einem Zeiger zuzuweisen, scheitert, da sie jedes Mal, wenn der Block erreicht wird, abweichen kann. Die Variable `a` wird als **statische** Variable deklariert und mit 2 initialisiert. Diese `a`-Variable befindet sich nicht in Konflikt mit `a` in `main`, da **statische** Variablen auf der internen Ebene nur innerhalb des Blocks sichtbar sind, in dem sie deklariert werden.  
  
 Die Variable `a` wird um 2 erhöht und ergibt 4. Wenn Sie die `other`-Funktion im selben Programm erneut aufrufen würden, wäre der Anfangswert von `a` 4. Interne **statische** Variablen behalten ihre Werte bei, wenn das Programm beendet wird, und werden dann erneut in den Block, in dem sie deklariert werden, eingegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Speicherklassenspezifizierer für Deklarationen der internen Ebene](../c-language/storage-class-specifiers-for-internal-level-declarations.md)

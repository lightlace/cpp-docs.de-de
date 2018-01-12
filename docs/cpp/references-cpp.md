---
title: Verweise (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- objects [C++], referencing
- references [C++]
- references, to pointers
- declarations, references
- references, declaring
- referencing objects, declarator syntax
ms.assetid: 68156f7f-97a0-4b66-b26d-b25ade5e3bd8
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e7453fbab0ade6cfe2cbdd836d7d59ba49c3ccfd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="references-c"></a>Verweise (C++)
Ein Verweis, z. B. ein Zeiger ist, speichert die Adresse eines Objekts, das sich an anderer Stelle im Speicher befindet. Im Gegensatz zu einem Zeiger kann sich ein Verweis nach der Initialisierung nicht auf ein anderes Objekt beziehen oder auf null gesetzt werden. Es gibt zwei Arten von verweisen: Lvalue-Verweise, die auf einer benannten Variablen und Rvalue-Verweise, die zum beziehen verweisen einer [temporäres Objekt](../cpp/temporary-objects.md). Der &-Operator gibt einen Lvalue-Verweis und der & &-Operator gibt einen Rvalue-Verweis oder einen universellen Verweis (Rvalue oder Lvalue) je nach Kontext.  
  
 Verweise können mit der folgenden Syntax deklariert werden:  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers   
[ms-modifier] declarator [= expression];  
```  
  
 Jeder gültige Deklarator, der einen Verweis angibt, kann verwendet werden. Sofern der Verweis kein Verweis auf den Funktions- oder Arraytyp ist, gilt die folgende vereinfachte Syntax:  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers [& or &&]   
[cv-qualifiers] identifier [= expression];  
```  
  
 Verweise werden unter Verwendung dieser Reihenfolge deklariert:  
  
 1. Die Deklarationsspezifizierer:  
  
-   Ein optionaler Speicherklassenbezeichner.  
  
-   Optionale **const** und/oder `volatile` Qualifizierer.  
  
-   Der Typspezifizierer: der Name eines Typs  
  
-   2. Der Deklarator:  
  
-   Ein optionaler Microsoft-spezifischer Modifizierer. Weitere Informationen finden Sie unter [Microsoft-spezifische Modifizierer](../cpp/microsoft-specific-modifiers.md).  
  
-   Der &-Operator oder & &-Operator.  
  
-   Optionale **const** und/oder `volatile` Qualifizierer.  
  
-   Der Bezeichner.  
  
 3. Ein optionaler Initialisierer.  
  
 Die komplexeren deklaratorformen für Zeiger auf Arrays und Funktionen auch für Verweise auf Arrays und Funktionen gelten finden Sie unter [Zeiger](../cpp/pointers-cpp.md) und [Deklaratoren](http://msdn.microsoft.com/en-us/8a7b9b51-92bd-4ac0-b3fe-0c4abe771838).  
  
 Mehrere Deklaratoren und Initialisierer erscheinen möglicherweise in einer durch Trennzeichen getrennten Liste, die einem einzelnen Deklarationsspezifizierer folgt. Zum Beispiel:  
  
```  
int &i;   
int &i, &j;   
```  
  
 Verweise, Zeiger und Objekte können zusammen deklariert werden:  
  
```  
int &ref, *ptr, k;   
```  
  
 Ein Verweis enthält die Adresse eines Objekts, verhält sich aber syntaktisch wie ein Objekt.  
  
 Beachten Sie im folgenden Programm, dass der Name des Objekts `Today` und der Verweis auf das Objekt `TodayRef` in Programmen identisch verwendet werden kann:  
  
## <a name="example"></a>Beispiel  
  
```  
// references.cpp  
#include <stdio.h>  
struct S {  
   short i;  
};  
  
int main() {  
   S  s;   // Declare the object.  
   S& SRef = s;   // Declare the reference.  
   s.i = 3;  
  
   printf_s("%d\n", s.i);  
   printf_s("%d\n", SRef.i);  
  
   SRef.i = 4;  
   printf_s("%d\n", s.i);  
   printf_s("%d\n", SRef.i);  
}  
```  
  
```Output  
3  
3  
4  
4  
```  
  
## <a name="comment"></a>Kommentar  
 Themen in diesem Abschnitt:  
  
-   [Verweistyp-Funktionsargumente](../cpp/reference-type-function-arguments.md)  
  
-   [Verweistyp-Funktionsrückgaben](../cpp/reference-type-function-returns.md)  
  
-   [Verweise auf Zeiger](../cpp/references-to-pointers.md)  
  

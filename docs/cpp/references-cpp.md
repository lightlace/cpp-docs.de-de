---
title: "Verweise (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Deklarationen, Referenzen"
  - "Objekte [C++], Verweisen"
  - "Referenzen"
  - "Referenzen, Deklarieren"
  - "Referenzen, Auf Zeiger"
  - "Verweisen auf Objekte, Deklaratorsyntax"
ms.assetid: 68156f7f-97a0-4b66-b26d-b25ade5e3bd8
caps.latest.revision: 12
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Verweise (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Verweis, z. B. ein Zeiger ist, speichert die Adresse eines Objekts, das sich an anderer Stelle im Speicher befindet.  Im Gegensatz zu einem Zeiger kann sich ein Verweis nach der Initialisierung nicht auf ein anderes Objekt beziehen oder auf null gesetzt werden.  Es gibt zwei Arten von Verweisen: Lvalue\-Verweise, die sich auf benannte Variable beziehen und Rvalue\-Verweise, die sich auf ein [temporäres Objekt](../cpp/temporary-objects.md) beziehen.  Der &\-Operator gibt einen Lvalue\-Verweis und der & &\-Operator gibt einen Rvalue\-Verweis oder einen universellen Verweis \(Rvalue oder Lvalue\) je nach Kontext.  
  
 Verweise können mit der folgenden Syntax deklariert werden:  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers   
[ms-modifier] declarator [= expression];  
```  
  
 Jeder gültige Deklarator, der einen Verweis angibt, kann verwendet werden.  Sofern der Verweis kein Verweis auf den Funktions\- oder Arraytyp ist, gilt die folgende vereinfachte Syntax:  
  
```  
[storage-class-specifiers] [cv-qualifiers] type-specifiers [& or &&]   
[cv-qualifiers] identifier [= expression];  
```  
  
 Verweise werden unter Verwendung dieser Reihenfolge deklariert:  
  
 1.  Die Deklarationsspezifizierer:  
  
-   Ein optionaler Speicherklassenbezeichner.  
  
-   Optionale **const**\- und\/oder `volatile`\-Qualifizierer  
  
-   Der Typspezifizierer: der Name eines Typs  
  
-   2.  Der Deklarator:  
  
-   Ein optionaler Microsoft\-spezifischer Modifizierer.  Weitere Informationen finden Sie unter [Microsoft\-spezifische Modifizierer](../cpp/microsoft-specific-modifiers.md).  
  
-   Der &\-Operator oder & &\-Operator.  
  
-   Optionale **const**\- und\/oder `volatile`\-Qualifizierer  
  
-   Der Bezeichner.  
  
 3.  Ein optionaler Initialisierer.  
  
 Die komplexeren Deklaratorformen für Zeiger auf Arrays und Funktionen gelten auch für Verweise auf Arrays und Funktionen. Weitere Informationen finden Sie unter [Zeiger](../cpp/pointers-cpp.md) und [Deklaratoren](assetId:///8a7b9b51-92bd-4ac0-b3fe-0c4abe771838).  
  
 Mehrere Deklaratoren und Initialisierer erscheinen möglicherweise in einer durch Trennzeichen getrennten Liste, die einem einzelnen Deklarationsspezifizierer folgt.  Zum Beispiel:  
  
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
  
## Beispiel  
  
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
  
  **3**  
**3**  
**4**  
**4**   
## Kommentar  
 Themen in diesem Abschnitt:  
  
-   [Verweistyp\-Funktionsargumente](../cpp/reference-type-function-arguments.md)  
  
-   [Verweistyp\-Funktionsrückgaben](../cpp/reference-type-function-returns.md)  
  
-   [Verweise auf Zeiger](../cpp/references-to-pointers.md)  
  
## Siehe auch  
 [Initialisieren von Verweisen](../misc/initializing-references.md)
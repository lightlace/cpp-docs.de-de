---
title: "make_public"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.make_public"
  - "make_public_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "make_public-Pragma"
  - "Pragmas, make_public"
ms.assetid: c3665f4d-268a-4932-9661-c37c8ae6a341
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# make_public
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass für einen systemeigenen Typ der öffentliche Assemblyzugriff gewährt wird.  
  
## Syntax  
  
```  
#pragma make_public(type)  
```  
  
#### Parameter  
 `type` ist der Name des Typs, der den öffentlichen Assemblyzugriff aufweisen soll.  
  
## Hinweise  
 `make_public` ist sinnvoll, wenn der systemeigene Typ, auf den Sie verweisen möchten, aus einer H\-Datei stammt, die Sie nicht ändern können.  Soll der systemeigene Typ in der Signatur einer öffentlichen Funktion in einem Typ mit öffentlicher Assemblysichtbarkeit verwendet werden, muss der systemeigene Typ auch über den öffentlichen Assemblyzugriff verfügen, sonst gibt der Compiler eine Warnung aus.  
  
 `make_public` muss im globalen Bereich angegeben werden und ist nur wirksam von diesem Deklarationspunkt bis zum Ende der Quellcodedatei.  
  
 Der systemeigene Typ kann implizit oder explizit privat sein, weitere Informationen finden Sie unter [Typsichtbarkeit](../misc/type-visibility.md).  
  
## Beispiel  
 Beim folgenden Beispiel handelt es sich um die Inhalte einer H\-Datei, welche die Definitionen für zwei systemeigene Strukturen enthält.  
  
```  
// make_public_pragma.h  
struct Native_Struct_1 { int i; };  
struct Native_Struct_2 { int i; };  
```  
  
## Beispiel  
 Das folgende Codebeispiel verwendet die Headerdatei und veranschaulicht, dass der Compiler – sofern die systemeigenen Strukturen nicht explizit unter Verwendung von `make_public` als öffentlich gekennzeichnet sind – eine Warnung generiert, wenn Sie versuchen, die systemeigenen Strukturen in der Signatur einer öffentlicher Funktion in einem öffentlichen verwalteten Typ zu verwenden.  
  
```  
// make_public_pragma.cpp  
// compile with: /c /clr /W1  
#pragma warning (default : 4692)  
#include "make_public_pragma.h"  
#pragma make_public(Native_Struct_1)  
  
public ref struct A {  
   void Test(Native_Struct_1 u) {u.i = 0;}   // OK  
   void Test(Native_Struct_2 u) {u.i = 0;}   // C4692  
};  
```  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
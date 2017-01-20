---
title: "Zugreifen auf C- oder C++-Daten in __asm-Bl&#246;cken"
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
helpviewer_keywords: 
  - "__asm-Schlüsselwort [C++], Datenmember"
  - "Datenzugriff [C++], In __asm-Blöcken"
  - "Datenmember [C++], In __asm-Blöcken"
  - "Strukturtypen in __asm-Blöcken"
ms.assetid: e99f5a28-0381-4090-8ece-6af8f2436a49
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Zugreifen auf C- oder C++-Daten in __asm-Bl&#246;cken
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Eine große Hilfe der Inline\- Assemblys ist die Fähigkeit, C\# oder C\+\+\-Variablen anhand ihres Namens zugreifen.  Ein `__asm`\-Block kann alle Symbole, einschließlich Variablennamen verweisen, die im Bereich enthalten sind, in dem der Block erscheint.  Wenn z. B. C `var`\-Variable im Gültigkeitsbereich befindet, durch die Anweisung  
  
```  
__asm mov eax, var  
```  
  
 speichert den Wert von `var` in EAX.  
  
 Wenn eine Klassen\-, Struktur\- oder Unionmember über einen eindeutigen Namen verfügt, kann ein `__asm`\-Block diesen Member nur mit dem Namen verweisen, ohne dass die Variable oder den Namen angeben `typedef` vor dem Operator des Punkts \(.\)**.** Wenn jedoch der Membername nicht eindeutig ist, müssen Sie eine Variable oder einen `typedef` Namen direkt vor den Punktoperator platzieren.  Um beispielsweise die Freigabe von Strukturtypen in der folgenden Beispiel `same_name` als dem Membernamen.:  
  
 Wenn Sie Variablen mit den Typen deklarieren  
  
```  
struct first_type hal;  
struct second_type oat;  
```  
  
 Alle Verweise auf den Member `same_name` müssen den Variablennamen verwenden, da `same_name` nicht eindeutig ist.  Wenn der Member `weasel` über einen eindeutigen Namen verfügt, können Sie ihn nur mithilfe seines Namens der Member zugreifen:  
  
```  
// InlineAssembler_Accessing_C_asm_Blocks.cpp  
// processor: x86  
#include <stdio.h>  
struct first_type  
{  
   char *weasel;  
   int same_name;  
};  
  
struct second_type  
{  
   int wonton;  
   long same_name;  
};  
  
int main()  
{  
   struct first_type hal;  
   struct second_type oat;  
  
   __asm  
   {  
      lea ebx, hal  
      mov ecx, [ebx]hal.same_name ; Must use 'hal'  
      mov esi, [ebx].weasel       ; Can omit 'hal'  
   }  
   return 0;  
}  
```  
  
 Wenn Sie den Variablennamen ist nicht nur eine Art bequemlichkeit.  Die gleichen Assemblyanweisungen werden generiert, ob der Variablenname vorhanden ist.  
  
 Sie können Member auf Daten in C\+\+ ohne Berücksichtigung Zugriffsbeschränkungen.  Sie können jedoch keine Memberfunktionen aufrufen.  
  
 **Microsoft ENDES bestimmten**  
  
## Siehe auch  
 [Verwenden von C oder C\+\+ in \_\_asm\-Blöcken](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)
---
title: Zugreifen auf C- oder C++-Daten in __asm-Blöcken | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data members [C++], in __asm blocks
- data access [C++], in __asm blocks
- __asm keyword [C++], data members
- structure types in __asm blocks
ms.assetid: e99f5a28-0381-4090-8ece-6af8f2436a49
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9631db3c09c19e38791a6c909be02acd1c91601b
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32049758"
---
# <a name="accessing-c-or-c-data-in-asm-blocks"></a>Zugreifen auf C- oder C++-Daten in __asm-Blöcken
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Zur Vereinfachung von Inlineassemblys hervorragende ist die Möglichkeit zum Verweisen auf C- oder C++-Variablen anhand des Namens. Ein `__asm` Block ersehen Symbole, einschließlich der Variablennamen, die im Bereich befinden, in dem der Block wird angezeigt. Für die Instanz, wenn die C-Variablen `var` im Gültigkeitsbereich befindet, die Anweisung  
  
```  
__asm mov eax, var  
```  
  
 Speichert den Wert des `var` in EAX.  
  
 Wenn eine Klasse, Struktur oder union-Member einen eindeutigen Namen verfügt über eine `__asm` Block kann nur die Elementnamen, ohne die Variable mit verweisen oder `typedef` Namen vor dem Punkt (**.**) Operator. Wenn der Membernamen nicht eindeutig ist, aber Sie müssen platzieren eine Variablen oder `typedef` Name unmittelbar vor dem Period-Operator. Z. B. die Strukturtypen im folgenden Beispiel nutzen gemeinsam `same_name` als ihre Elementname:.  
  
 Wenn Sie Variablen mit den Typen deklarieren  
  
```  
struct first_type hal;  
struct second_type oat;  
```  
  
 alle Verweise auf das Element `same_name` der Variablenname muss verwendet werden, da `same_name` ist nicht eindeutig. Das Element, aber `weasel` verfügt über einen eindeutigen Namen, damit Sie es nur unter Verwendung seiner Member verwenden können:  
  
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
  
 Beachten Sie, dass das Weglassen der Variablenname lediglich Codierung zur Vereinfachung. Die gleiche Assemblyanweisungen generiert werden, und zwar unabhängig davon, ob der Variablenname vorhanden ist.  
  
 Sie können unabhängig von der zugriffsbeschränkungen-Datenmember in C++ zugreifen. Allerdings können keine Sie Memberfunktionen aufrufen.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von C oder C++ in __asm-Blöcken](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)
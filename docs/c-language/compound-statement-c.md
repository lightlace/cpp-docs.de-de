---
title: Verbundanweisung (C) | Microsoft-Dokumentation
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
- compound statements
- statements, compound
ms.assetid: 32d1bf86-cbbc-42a9-ba3a-1be1c6c7754c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9422e3229aa5e800859f50e1ca058e32a4120074
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compound-statement-c"></a>Verbundanweisung (C)
Eine Verbundanweisung (auch „Block“ genannt) wird in der Regel als Text einer anderen Anweisung, wie der **if**-Anweisung, angezeigt. [Deklarationen und Typen](../c-language/declarations-and-types.md) beschreibt die Form und die Bedeutung der Deklarationen, die am Anfang einer Verbundanweisung angezeigt werden können.  
  
## <a name="syntax"></a>Syntax  
 *compound-statement*:  
 **{**  *declaration-list* opt*statement-list*opt**}**  
  
 *declaration-list*:  
 *declaration*  
  
 *declaration-list-Deklaration*  
  
 *statement-list*:  
 s*tatement*  
  
 *statement-list-Anweisung*  
  
 Wenn Deklarationen vorhanden sind, müssen sie vor allen Anweisungen stehen. Der Gültigkeitsbereich eines Bezeichners, der am Anfang einer Verbundanweisung deklariert ist, reicht vom Deklarationspunkt bis an das Ende des Blocks. Es ist im gesamten Block sichtbar, es sei denn, eine Deklaration des gleichen Bezeichners ist in einem inneren Block vorhanden.  
  
 Für Bezeichner in einer Verbundanweisung wird **auto** vorausgesetzt, es sei denn, sie sind explizit als **register**, **static** oder `extern` deklariert. Ausnahmen sind Funktionen, die nur `extern` sein können. Sie können den `extern`-Spezifizierer in Funktionsdeklarationen weglassen. Die Funktion ist dann immer noch `extern`.  
  
 Der Speicher wird nicht zugeordnet und eine Initialisierung ist nicht zulässig, wenn eine Variable oder Funktion in einer Verbundanweisung mit der `extern`-Speicherklasse deklariert ist. Die Deklaration verweist auf eine externe Variable oder Funktion, die an einer anderen Stelle definiert ist.  
  
 Variablen, die in einem Block mit dem **auto**- oder **register**-Schlüsselwort deklariert werden, werden neu zugeordnet und bei Bedarf jedes Mal initialisiert, wenn die Verbundanweisung eingegeben wird. Diese Variablen werden nicht definiert, nachdem die Verbundanweisung beendet wurde. Wenn eine Variable, die in einem Block deklariert wird, das Attribut **static** besitzt, wird die Variable zu Beginn der Programmausführung initialisiert und behält ihren Wert während des Programmablaufs. Weitere Informationen zu **static** erhalten Sie unter [Speicherklassen](../c-language/c-storage-classes.md).  
  
 In diesem Beispiel wird eine Verbundanweisung veranschaulicht:  
  
```  
if ( i > 0 )   
{  
    line[i] = x;  
    x++;  
    i--;  
}  
```  
  
 In diesem Beispiel werden alle Anweisungen innerhalb einer Verbundanweisung in der Reihenfolge ausgeführt, wenn `i` größer als 0 ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen](../c-language/statements-c.md)
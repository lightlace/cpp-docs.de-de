---
title: Typkonvertierungen (C) | Microsoft-Dokumentation
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
- conversions, type
- type conversion
- converting types
- integral promotions
- type casts, when performed
ms.assetid: d130ee7c-03c3-48f4-af7b-1fdba0d3b086
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b1e4dede1dab1fcaf9ae4de5846539924d0095e4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="type-conversions-c"></a>Typkonvertierungen (C)
Typkonvertierungen hängen vom angegebenen Operator und dem Typ des Operanden bzw. der Operatoren ab. Typkonvertierungen werden in folgenden Fällen ausgeführt:  
  
-   Wenn ein Wert eines Typs einer Variablen eines anderen Typs zugewiesen wird oder wenn ein Operator den Typ des bzw. der Operanden vor der Durchführung des Vorgangs konvertiert.  
  
-   Wenn ein Wert eines Typs explizit in einen anderen Typ umgewandelt wird.  
  
-   Wenn ein Wert als Argument an eine Funktion übergeben wird oder wenn ein Typ von einer Funktion zurückgegeben wird.  
  
 Ein Zeichen, eine kurze ganze Zahl oder ein ganzzahliges Bitfeld (alle entweder signiert oder unsigniert) oder ein Objekt des Enumerationstyps können immer dann in einem Ausdruck verwendet werden, wenn die Verwendung einer Ganzzahl möglich ist. Wenn ein `int`-Wert alle Werte des ursprünglichen Typs darstellen kann, wird der Wert in `int` konvertiert. Andernfalls wird er in `unsigned int` konvertiert. Dieser Vorgang wird als "ganzzahlige Erweiterung" bezeichnet. Ganzzahlige Erweiterungen behalten den Wert bei. Das heißt, es ist gewährleistet, dass der Wert nach der Erweiterung derselbe ist wie vor der Erweiterung. Weitere Informationen finden Sie unter [Übliche arithmetische Konvertierungen](../c-language/usual-arithmetic-conversions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Ausdrücke und Zuweisungen](../c-language/expressions-and-assignments.md)
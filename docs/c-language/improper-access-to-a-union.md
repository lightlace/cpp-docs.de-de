---
title: "Unsachgemäßer Zugriff auf eine Union | Microsoft-Dokumentation"
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
ms.assetid: b273d984-62a8-4003-9a87-bf0149d3f2dd
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 9e3bd236cfc6675f9476a0127977e329af3698af
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="improper-access-to-a-union"></a>Unsachgemäßer Zugriff auf eine Union
**ANSI 3.3.2.3** Auf ein Member eines union-Objekts wird mithilfe eines Members eines anderen Typs zugegriffen  
  
 Wenn eine Union von zwei Typen deklariert wird und ein Wert gespeichert ist, aber mit dem anderen Typ auf die Union zugegriffen wird, sind die Ergebnisse unzuverlässig.  
  
 Beispielsweise wird eine Union von **float** und `int` deklariert. Ein **float**-Wert wird gespeichert, aber später greift das Programm auf den Wert als `int` zu. In einer solchen Situation ist der Wert der internen Speicherung von **float**-Werten abhängig. Der Ganzzahlwert wäre nicht zuverlässig.  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Unions, Enumerationen und Bitfelder](../c-language/structures-unions-enumerations-and-bit-fields.md)

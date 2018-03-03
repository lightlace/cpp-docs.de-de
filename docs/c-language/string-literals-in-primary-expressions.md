---
title: "Zeichenfolgenliterale in primären Ausdrücken | Microsoft-Dokumentation"
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
- string literals, in primary expressions
ms.assetid: 3ec31278-527b-40d2-8c83-6b09e2d81ca6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0920280f672b1c45d317ade4c592a6b93356fb8f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="string-literals-in-primary-expressions"></a>Zeichenfolgenliterale in primären Ausdrücken
Ein "Zeichenfolgenliteral" ist ein Zeichen, ein Breitzeichen oder eine Sequenz von angrenzenden Zeichen, die in Anführungszeichen gesetzt werden. Da es keine Variablen sind, können weder Zeichenfolgenliterale noch deren Elemente als linksseitige Operanden in einer Zuweisungsoperation verwendet werden. Der Typ eines Zeichenfolgenliterals ist ein Array von `char` (oder ein Array von `wchar_t` für Breitzeichenliterale). Arrays in Ausdrücken werden in Zeiger konvertiert. Weitere Informationen zu Zeichenfolgen finden Sie unter [Zeichenfolgenliterale](../c-language/c-string-literals.md).  
  
## <a name="see-also"></a>Siehe auch  
 [C-Ausdrücke (primär)](../c-language/c-primary-expressions.md)
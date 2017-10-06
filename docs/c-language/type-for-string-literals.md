---
title: Typ der Zeichenfolgenliterale | Microsoft-Dokumentation
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
- string literals, type
- types [C], string literals
ms.assetid: f50a28af-20c1-4440-bdc6-564c86a309c8
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 8e8d285bf85c711bd6adcbdb45c6384ea2309dc0
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="type-for-string-literals"></a>Typ für Zeichenfolgenliterale
Zeichenfolgenliterale haben ein Typarray von `char` (d.h. **char[ ]**). (Breitzeichenzeichenfolgen haben ein Typarray von `wchar_t` (d.h. **wchar_t[ ]**).) Dies bedeutet, dass eine Zeichenfolge ein Array mit Elementen vom Typ `char` ist. Die Anzahl der Elemente im Array entspricht der Anzahl von Zeichen in der Zeichenfolge plus einem beendenden Null-Zeichen.  
  
## <a name="see-also"></a>Siehe auch  
 [C-Zeichenfolgenliterale](../c-language/c-string-literals.md)

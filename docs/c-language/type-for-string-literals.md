---
title: Typ der Zeichenfolgenliterale | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- string literals, type
- types [C], string literals
ms.assetid: f50a28af-20c1-4440-bdc6-564c86a309c8
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cd43cd92dbc0580ab87e45ed77bae1c1798613c5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="type-for-string-literals"></a>Typ für Zeichenfolgenliterale
Zeichenfolgenliterale haben ein Typarray von `char` (d.h. **char[ ]**). (Breitzeichenzeichenfolgen haben ein Typarray von `wchar_t` (d.h. **wchar_t[ ]**).) Dies bedeutet, dass eine Zeichenfolge ein Array mit Elementen vom Typ `char` ist. Die Anzahl der Elemente im Array entspricht der Anzahl von Zeichen in der Zeichenfolge plus einem beendenden Null-Zeichen.  
  
## <a name="see-also"></a>Siehe auch  
 [C-Zeichenfolgenliterale](../c-language/c-string-literals.md)
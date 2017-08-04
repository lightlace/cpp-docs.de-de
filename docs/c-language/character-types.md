---
title: Zeichentypen | Microsoft-Dokumentation
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
- character data types [C]
- types [C], character
ms.assetid: d3ca8cda-c0d7-43af-9472-697e8ef015ce
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
ms.openlocfilehash: f0f8639e90787ddcc90b7a302f226d305f29dce1
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="character-types"></a>Zeichentypen
Eine ganzzahlige Zeichenkonstante, der nicht der Buchstabe **L** vorangestellt ist, ist vom Typ `int`. Der Wert einer ganzzahligen Zeichenkonstante, die ein einzelnes Zeichen enthält, ist der numerische Wert des Zeichens, das als ganze Zahl interpretiert wird. Beispielsweise ist der numerische Wert des Zeichens `a` 97 in dezimalen und 61 in hexadezimalen Zahlen.  
  
 Syntaktisch ist eine „Breitzeichenkonstante“ eine Zeichenkonstante, der der Buchstabe **L** vorangestellt ist. Eine Breitzeichenkonstante hat den Typ `wchar_t`, ein ganzzahliger Typ, der in der STDDEF.H-Headerdatei definiert ist. Zum Beispiel:  
  
```  
char    schar =  'x';   /* A character constant          */  
wchar_t wchar = L'x';   /* A wide-character constant for   
                            the same character           */  
```  
  
 Breitzeichenkonstanten sind 16 Bit breit und geben Member des erweiterten Ausführungszeichensatzes an. Sie ermöglichen es, Zeichen in Alphabeten auszudrücken, die zu groß sind, um durch den Typ `char` dargestellt zu werden. Weitere Informationen über Breitzeichen erhalten Sie unter [Multibyte- und Breitzeichen](../c-language/multibyte-and-wide-characters.md).  
  
## <a name="see-also"></a>Siehe auch  
 [C-Zeichenkonstanten](../c-language/c-character-constants.md)

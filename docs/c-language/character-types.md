---
title: Zeichentypen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- character data types [C]
- types [C], character
ms.assetid: d3ca8cda-c0d7-43af-9472-697e8ef015ce
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a48382f5f7a3ab64518c44ec953005cd54a4fe03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
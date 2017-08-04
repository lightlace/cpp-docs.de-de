---
title: Multibyte- und Breitzeichen | Microsoft-Dokumentation
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
- globalization [C++], character sets
- character data types [C]
- Unicode [C++], wide character set
- types [C], character
- characters [C++], wide
- international applications [C++], character display
- multibyte characters [C++]
- wide characters [C++]
- characters [C++], codes
- character codes [C++], wide
- character codes [C++], multibyte
ms.assetid: 1943c469-200d-4724-b18f-781d70520f9e
caps.latest.revision: 6
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
ms.openlocfilehash: d7dccb06867ede73bc5ef0a95c665e30211b0d97
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="multibyte-and-wide-characters"></a>Mehrbyte- und Breitzeichen
Ein Mehrbytezeichen ist ein Zeichen, das aus einem oder mehreren Bytesequenzen besteht. Jede Bytesequenz stellt ein einzelnes Zeichen im erweiterten Zeichensatz dar. Mehrbytezeichen werden in Zeichensätzen wie Kanji verwendet.  
  
 Breitzeichen sind mehrsprachige Zeichencodes, deren Breite immer 16 Bit beträgt. Der Typ für Zeichenkonstanten ist `char`. Der Typ ist für Breitzeichen ist `wchar_t`. Da Breitzeichen stets eine feste Größe aufweisen, vereinfachen diese das Programmieren mit internationalen Zeichensätzen.  
  
 Das Breitzeichen-Zeichenfolgenliteral `L"hello"` wird zu einem Array mit sechs Ganzzahlen vom Typ `wchar_t`.  
  
```  
{L'h', L'e', L'l', L'l', L'o', 0}  
```  
  
 Die Unicode-Spezifikation entspricht der Spezifikation für Breitzeichen. Die Laufzeitbibliotheksroutinen für Übersetzungen zwischen Multibyte- und Breitzeichen enthalten `mbstowcs`, `mbtowc`, `wcstombs` und `wctomb`.  
  
## <a name="see-also"></a>Siehe auch  
 [C-Bezeichner](../c-language/c-identifiers.md)

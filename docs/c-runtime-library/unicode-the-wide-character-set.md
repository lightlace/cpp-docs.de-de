---
title: 'Unicode: Der Breitzeichensatz | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.international
dev_langs: C++
helpviewer_keywords:
- Unicode [C++], wide character set
- wide characters [C++], Unicode
ms.assetid: b6a05a21-59a5-4d30-8c85-2dbe185f7a74
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5683cb5b161fd492afc69a93b6779b16c19c4022
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="unicode-the-wide-character-set"></a>Unicode: Der Breitzeichensatz
Ein Breitzeichen ist ein mehrsprachiger 2-Byte-Zeichencode. Alle in der modernen Computerwelt verwendeten Zeichen, einschließlich technischer Symbole und spezieller Veröffentlichungszeichen, können nach der Unicode-Spezifikation als Breitzeichen dargestellt werden. Der Unicode-Standard wurde von einem großen Konsortium entwickelt und überarbeitet, zu dem auch Microsoft gehört, und zählt heute zu den etablierten Standards.  
  
 Ein Breitzeichen weist den Typ `wchar_t` auf. Eine Breitzeichenzeichenfolge wird als `wchar_t[]`-Array dargestellt, auf das mit einem `wchar_t*`-Zeiger gezeigt wird. Sie können jedes ASCII-Zeichen als Breitzeichen darstellen, indem Sie den Buchstaben `L` dem Zeichen voranstellen. L'\0' ist beispielsweise das abschließende `NULL`-Breitzeichen (16 Bit). Auf ähnliche Weise können Sie jedes ASCII-Zeichenfolgenliteral als Breitzeichen-Zeichenfolgenliteral darstellen, indem Sie einfach den Buchstabe L dem ASCII-Literal voranstellen (L"Hello").  
  
 Im Allgemeinen nehmen Breitzeichen mehr Arbeitsspeicher in Anspruch als Multibytezeichen, werden aber schneller verarbeitet. Darüber hinaus kann jeweils nur ein Gebietsschema in der Multibytecodierung dargestellt werden, während alle Zeichensätze der Welt gleichzeitig von der Unicode-Darstellung dargestellt werden können.  
  
## <a name="see-also"></a>Siehe auch  
 [Internationalisierung](../c-runtime-library/internationalization.md)   
 [Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)
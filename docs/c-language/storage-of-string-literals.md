---
title: Speicherung von Zeichenfolgenliteralen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- string literals, storage
ms.assetid: ba5e4d2c-d456-44b3-a8ca-354af547ac50
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9d87998f7e9d579c012f5db2f38f20886c1e74c6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="storage-of-string-literals"></a>Speicherung von Zeichenfolgenliteralen
Die Zeichen einer Literalzeichenfolge werden in Reihenfolge an zusammenhängenden Speicherorten gespeichert. Eine Escapesequenz (wie z.B. **\\\\** oder **\\"**) innerhalb eines Zeichenfolgenliterals zählt als einzelnes Zeichen. Ein NULL-Zeichen (dargestellt durch die Escapesequenz **\0**) wird automatisch angefügt und markiert das Ende eines Zeichenfolgenliterals. (Dies geschieht bei [Übersetzungsphase](../preprocessor/phases-of-translation.md) 7.) Beachten Sie, dass der Compiler zwei identische Zeichenfolgen möglicherweise nicht an zwei verschiedenen Adressen speichert. [/GF](../build/reference/gf-eliminate-duplicate-strings.md) erzwingt, dass der Compiler eine einzige Kopie von identischen Zeichenfolgen in die ausführbare Datei einfügt.  
  
## <a name="remarks"></a>Hinweise  
 **Microsoft-spezifisch**  
  
 Zeichenfolgen haben eine statische Speicherdauer. Weitere Informationen über die Speicherdauer finden Sie unter [Speicherklassen](../c-language/c-storage-classes.md).  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [C-Zeichenfolgenliterale](../c-language/c-string-literals.md)
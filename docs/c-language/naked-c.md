---
title: Naked (C) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- naked keyword [C], storage-class attribute
- naked keyword [C]
- prolog code
- epilog code
ms.assetid: 23b1209b-93ba-46ad-a60f-2327c1933eaf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8a60cdec00f3109bfcc332feeaca24ba5d6880f9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383117"
---
# <a name="naked-c"></a>Naked (C)
**Microsoft-spezifisch**  
  
 Das naked-Speicherklassenattribut ist eine Microsoft-spezifische Erweiterung der Programmiersprache C. Der Compiler generiert Code ohne Prolog- und Epilogcode für Funktionen, die mit dem naked-Speicherklassenattribut deklariert werden. Naked-Funktionen sind hilfreich, wenn Sie eigene Prolog-/Epilogcodesequenzen mithilfe des Inlineassemblercodes schreiben müssen. Naked-Funktionen sind für das Schreiben von virtuellen Gerätetreibern hilfreich.  
  
 Spezielle Informationen zur Verwendung des naked-Attributs finden Sie unter [Naked-Funktionen](../c-language/naked-functions.md).  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [C-Speicherklassenattribute (erweitert)](../c-language/c-extended-storage-class-attributes.md)
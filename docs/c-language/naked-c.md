---
title: Naked (C) | Microsoft-Dokumentation
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
- naked keyword [C], storage-class attribute
- naked keyword [C]
- prolog code
- epilog code
ms.assetid: 23b1209b-93ba-46ad-a60f-2327c1933eaf
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 24266f2241ddb60d4a5403447a87caaa08ddaf08
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="naked-c"></a>Naked (C)
**Microsoft-spezifisch**  
  
 Das naked-Speicherklassenattribut ist eine Microsoft-spezifische Erweiterung der Programmiersprache C. Der Compiler generiert Code ohne Prolog- und Epilogcode für Funktionen, die mit dem naked-Speicherklassenattribut deklariert werden. Naked-Funktionen sind hilfreich, wenn Sie eigene Prolog-/Epilogcodesequenzen mithilfe des Inlineassemblercodes schreiben müssen. Naked-Funktionen sind für das Schreiben von virtuellen Gerätetreibern hilfreich.  
  
 Spezielle Informationen zur Verwendung des naked-Attributs finden Sie unter [Naked-Funktionen](../c-language/naked-functions.md).  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [C-Speicherklassenattribute (erweitert)](../c-language/c-extended-storage-class-attributes.md)

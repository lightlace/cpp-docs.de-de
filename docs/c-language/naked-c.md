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
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 2aa9ba1d3e6397a35389c2ee46ab30f19c0e6227
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="naked-c"></a>Naked (C)
**Microsoft-spezifisch**  
  
 Das naked-Speicherklassenattribut ist eine Microsoft-spezifische Erweiterung der Programmiersprache C. Der Compiler generiert Code ohne Prolog- und Epilogcode für Funktionen, die mit dem naked-Speicherklassenattribut deklariert werden. Naked-Funktionen sind hilfreich, wenn Sie eigene Prolog-/Epilogcodesequenzen mithilfe des Inlineassemblercodes schreiben müssen. Naked-Funktionen sind für das Schreiben von virtuellen Gerätetreibern hilfreich.  
  
 Spezielle Informationen zur Verwendung des naked-Attributs finden Sie unter [Naked-Funktionen](../c-language/naked-functions.md).  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [C-Speicherklassenattribute (erweitert)](../c-language/c-extended-storage-class-attributes.md)

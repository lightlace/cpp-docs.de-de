---
title: "Formatieren von Abs&#228;tzen in RichEdit-Steuerelementen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRichEditCtrl-Klasse, Absatzformatierung in"
  - "Formatierung [C++], Absätze"
  - "Absatzformatierung in CRichEditCtrl"
  - "Rich-Edit-Steuerelemente, Absatzformatierung in"
ms.assetid: 0df2e4c9-2074-4e41-b913-87cb8c1b4d43
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Formatieren von Abs&#228;tzen in RichEdit-Steuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können Memberfunktionen des Rich\-Edit\-Steuerelements \([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)\) werden Absätze zu formatieren und Formatierungsinformationen abzurufen.  Absatzformatierungsattributeinschließungsausrichtung, \-Registerkarten, \-Einzüge und \-Nummerierung.  
  
 Sie können Absatzformatierung anwenden, indem Sie die Memberfunktion [SetParaFormat](../Topic/CRichEditCtrl::SetParaFormat.md) verwenden.  Um die aktuelle Absatzformatierung für den markierten Text zu bestimmen, verwenden Sie die [GetParaFormat](../Topic/CRichEditCtrl::GetParaFormat.md)\-Memberfunktion.  Die [PARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787940)\-Struktur wird mit dieser Memberfunktionen verwendet, um anzugeben Absatzformatvorlagen verwendet.  Einer der wichtigen Member von **PARAFORMAT** ist **dwMask**.  In `SetParaFormat` gibt an, welche **dwMask** Absatzstile von diesem Funktionsaufruf eingerichtet werden.  `GetParaFormat` meldet die Attribute des ersten Absatzes in der Auswahl; **dwMask** gibt den Attributen an, die während der Auswahl konsistent sind.  
  
## Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)
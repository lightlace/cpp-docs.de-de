---
title: "Wortumbrüche in RichEdit-Steuerelementen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CRichEditCtrl class [MFC], word breaks in
- word breaks
- breaking words in CRichEditCtrl
- rich edit controls [MFC], word breaks in
ms.assetid: 641dcf9e-7b40-4dc0-85f7-575a8c142f73
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 12ae5d682515a6f266b7e41a2ff89148ea98c0b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="word-breaks-in-rich-edit-controls"></a>Wortumbrüche in RichEdit-Steuerelementen
Ein Rich-edit-Steuerelement ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) Ruft eine Funktion mit dem Namen einer Prozedur"Break Word" Umbrüche zwischen Wörtern zu suchen und bestimmen, in denen Zeilen unterbrochen werden kann. Das Steuerelement verwendet diese Informationen, wenn Zeilenumbruch Vorgänge ausgeführt, und bei der Verarbeitung der Tastenkombination STRG + nach-links- und STRG + nach-rechts. Eine Anwendung kann senden Nachrichten an ein rich-Edit-Steuerelement, ersetzen Sie die standardmäßige Wortumbrüchen Prozedur, um Wortumbrüchen Informationen abzurufen und um zu bestimmen, was ein angegebenes Zeichen Zeile liegt.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)


---
title: "Streamen von Vorgängen in RichEdit-Steuerelementen | Microsoft Docs"
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
- CRichEditCtrl class [MFC], stream operations
- CRichEditCtrl class [MFC], stream storage
- rich edit controls [MFC], stream operations
- storage, stream in CRichEditCtrl
- stream operations in CRichEditCtrl
- stream storage and CRichEditCtrl
ms.assetid: 110b4684-1e76-4ca6-9ef0-5bc8b2d93c78
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c1a73790124adbc1ff8a89290bf4e1d7a4fa6824
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="stream-operations-in-rich-edit-controls"></a>Streamoperationen in RichEdit-Steuerelementen
Können Sie Streams zum Übertragen von Daten in oder aus einem rich-Edit-Steuerelement ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Ein Datenstrom wird definiert, indem ein [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) -Struktur, die einen Puffer und eine anwendungsdefinierte Rückruffunktion angibt.  
  
 Zum Lesen von Daten in einem Rich edit-Steuerelement (d. h. die Daten im stream), verwenden Sie die [Memberfunktion StreamIn](../mfc/reference/cricheditctrl-class.md#streamin) Memberfunktion. Das Steuerelement ruft wiederholt die anwendungsdefinierte Rückruffunktion, einen Teil der Daten in den Puffer jedes Mal übertragen.  
  
 Zum Speichern der Inhalte von einem Rich-edit-Steuerelement (d. h. Daten streamen), können Sie die [Memberfunktion StreamOut](../mfc/reference/cricheditctrl-class.md#streamout) Memberfunktion. Das Steuerelement in den Puffer wiederholt schreibt und ruft dann die Anwendung definierten Rückruffunktion. Für jeden Aufruf speichert die Rückruffunktion den Inhalt des Puffers.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)


---
title: Stream-Vorgänge in RichEdit-Steuerelementen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f418156fb5be4837bc0dbe9b05b3ad26d7ac02dd
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43196857"
---
# <a name="stream-operations-in-rich-edit-controls"></a>Streamoperationen in RichEdit-Steuerelementen
Sie können die Streams verwenden, zum Übertragen von Daten in oder aus einem rich Edit-Steuerelement ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Ein Datenstrom wird definiert, indem ein [EDITSTREAM](/windows/desktop/api/richedit/ns-richedit-_editstream) -Struktur, die einen Puffer und einer anwendungsdefinierten Rückruffunktion angibt.  
  
 Zum Lesen von Daten in einem Rich edit-Steuerelement (d. h. die Daten im stream), verwenden Sie die [Memberfunktion StreamIn](../mfc/reference/cricheditctrl-class.md#streamin) Member-Funktion. Das Steuerelement ruft wiederholt die anwendungsdefinierten Rückruffunktion, die einen Teil der Daten in den Puffer, jedes Mal überträgt.  
  
 Zum Speichern der Inhalte von einem Rich-edit-Steuerelement (d. h. beim Streamen der Daten), können Sie die [Memberfunktion StreamOut](../mfc/reference/cricheditctrl-class.md#streamout) Member-Funktion. Das Steuerelement wiederholt schreibt in den Puffer und ruft dann die anwendungsdefinierten Rückruffunktion. Für jeden Aufruf speichert die Callback-Funktion den Inhalt des Puffers.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)


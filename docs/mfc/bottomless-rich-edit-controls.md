---
title: Unbeschränkte Rich-Edit-Steuerelemente
ms.date: 11/04/2016
helpviewer_keywords:
- bottomless rich edit controls
- rich edit controls [MFC], bottomless
- CRichEditCtrl class [MFC], bottomless
ms.assetid: 2877dd32-1e9a-4fd1-98c0-66dcbbeef1de
ms.openlocfilehash: 4affdbeed723ea83beda785116dc4c45771073b2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509152"
---
# <a name="bottomless-rich-edit-controls"></a>Unbeschränkte Rich-Edit-Steuerelemente

Die Größe eines Rich-Edit-Steuer Elements ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) kann von Ihrer Anwendung nach Bedarf geändert werden, sodass es immer die gleiche Größe wie der Inhalt hat. Ein Rich Edit-Steuerelement unterstützt diese so genannte "nicht unterstützte" Funktion, indem das übergeordnete Fenster eine [EN_REQUESTRESIZE](/windows/win32/Controls/en-requestresize) -Benachrichtigungs Meldung sendet, wenn sich die Größe seines Inhalts ändert.

Bei der Verarbeitung der **EN_REQUESTRESIZE** -Benachrichtigungs Meldung sollte eine Anwendung die Größe des Steuer Elements auf die Dimensionen in der angegebenen [reqresize](/windows/win32/api/richedit/ns-richedit-reqresize) -Struktur ändern. Eine Anwendung kann auch alle Informationen in der Nähe des Steuer Elements verschieben, um die Änderung der Höhe des Steuer Elements zu ermöglichen. Um die Größe des Steuer Elements zu ändern, können `CWnd` Sie die Funktion [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos)verwenden.

Zum Senden einer **EN_REQUESTRESIZE** -Benachrichtigungs Meldung mithilfe der Member-Funktion von [RequestResize](../mfc/reference/cricheditctrl-class.md#requestresize) können Sie ein nicht verarbeiteter Rich-Edit-Steuerelement erzwingen. Diese Meldung kann im [OnSize](../mfc/reference/cwnd-class.md#onsize) -Handler nützlich sein.

Um **EN_REQUESTRESIZE** -Benachrichtigungs Meldungen zu empfangen, müssen Sie die Benachrichtigung mithilfe `SetEventMask` der Member-Funktion aktivieren.

## <a name="see-also"></a>Siehe auch

[Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

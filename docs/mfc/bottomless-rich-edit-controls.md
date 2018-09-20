---
title: Unbeschränkte Rich-Edit-Steuerelemente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- bottomless rich edit controls
- rich edit controls [MFC], bottomless
- CRichEditCtrl class [MFC], bottomless
ms.assetid: 2877dd32-1e9a-4fd1-98c0-66dcbbeef1de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9ce3922bfd1a86864886057a4457627547fe85e0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373349"
---
# <a name="bottomless-rich-edit-controls"></a>Unbeschränkte Rich-Edit-Steuerelemente

Ihre Anwendung kann die Größe ein rich-Edit-Steuerelements ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) nach Bedarf, sodass sie immer die gleiche Größe wie der Inhalt ist. Ein rich-Edit-Steuerelement unterstützt diese so genannte "grenzenlosen"-Funktion, indem Sie das übergeordnete Fenster sendet eine [EN_REQUESTRESIZE](/windows/desktop/Controls/en-requestresize) Benachrichtigung, wenn sich die Größe des Inhalts ändert.

Bei der Verarbeitung der **EN_REQUESTRESIZE** -benachrichtigungsmeldung und eine Anwendung sollte das Steuerelement, das die Dimensionen in der angegebenen Größe [REQRESIZE](/windows/desktop/api/richedit/ns-richedit-_reqresize) Struktur. Eine Anwendung möglicherweise auch verschieben, alle Informationen neben dem Steuerelement um Änderung der Höhe des Steuerelements zu berücksichtigen. Zum Ändern der Größe des Steuerelements können Sie die `CWnd` Funktion [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos).

Sie können erzwingen, dass eine unbeschränkte rich-Edit-Steuerelement zum Senden einer **EN_REQUESTRESIZE** benachrichtigungsmeldung mithilfe der [RequestResize](../mfc/reference/cricheditctrl-class.md#requestresize) Member-Funktion. Diese Meldung kann nützlich sein, die [OnSize](../mfc/reference/cwnd-class.md#onsize) Handler.

Zum Empfangen von **EN_REQUESTRESIZE** benachrichtigungsmeldungen, müssen Sie die Benachrichtigung aktivieren, mit der `SetEventMask` Member-Funktion.

## <a name="see-also"></a>Siehe auch

[Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)


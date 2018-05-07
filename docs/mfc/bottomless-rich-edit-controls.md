---
title: Unbeschränkte Rich-Edit-Steuerelemente | Microsoft Docs
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
ms.openlocfilehash: 6f2b08f6c04d345b4ae3ab32c6d0f17a1d8a4647
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="bottomless-rich-edit-controls"></a>Unbeschränkte Rich-Edit-Steuerelemente
Ihre Anwendung kann ein rich-Edit-Steuerelement die Größe ändern ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) nach Bedarf, sodass sie immer die gleiche Größe wie der Inhalt ist. Ein rich-Edit-Steuerelement unterstützt diese so genannten "Unbeschränkte" Funktionalität durch das übergeordnete Fenster sendet eine [EN_REQUESTRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb787983) Benachrichtigung bei jeder Änderung der Größe ihrer Inhalte.  
  
 Bei der Verarbeitung der **EN_REQUESTRESIZE** benachrichtigungsmeldung, eine Anwendung sollte das Steuerelement auf die Dimensionen in der angegebenen Größe [REQRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb787950) Struktur. Eine Anwendung kann auch verschieben, alle Informationen, die neben dem Steuerelement um Änderung der Höhe des Steuerelements zu berücksichtigen. Um die Größe des Steuerelements, können Sie die `CWnd` Funktion [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos).  
  
 Sie können erzwingen, dass eine unbeschränkte rich-Edit-Steuerelement zum Senden einer **EN_REQUESTRESIZE** benachrichtigungsmeldung mithilfe der [RequestResize](../mfc/reference/cricheditctrl-class.md#requestresize) Memberfunktion. Diese Meldung kann in nützlich sein, die [OnSize](../mfc/reference/cwnd-class.md#onsize) Handler.  
  
 Zum Empfangen von **EN_REQUESTRESIZE** benachrichtigungsmeldungen, müssen Sie die Benachrichtigung aktivieren, mit der `SetEventMask` Memberfunktion.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)


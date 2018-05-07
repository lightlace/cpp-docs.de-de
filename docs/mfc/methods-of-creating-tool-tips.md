---
title: Methoden zum Erstellen von QuickInfos | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CToolTipCtrl class [MFC], creating tool tips
- tool tips [MFC], tool tip controls
- tool tips [MFC], creating
ms.assetid: b015e9f4-ddfb-49a4-a5a6-fa2d45e4d328
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 26f6e7cbf8c6464afa90c52f9cd91dcdb55de767
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="methods-of-creating-tool-tips"></a>Methoden zum Erstellen von QuickInfos
MFC stellt drei Klassen zum Erstellen und verwalten das Tool QuickInfo-Steuerelement: [CWnd](../mfc/reference/cwnd-class.md), [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md), [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) und [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md). Die QuickInfo-Memberfunktionen in diesen Klassen zu umschließen die allgemeine Windows-Steuerungs-API. Klasse `CToolBarCtrl` und Klasse `CToolTipCtrl` Klasse abgeleitet sind `CWnd`.  
  
 `CWnd` stellt vier Memberfunktionen zum Erstellen und Verwalten von QuickInfos bereit: [EnableToolTips](../mfc/reference/cwnd-class.md#enabletooltips), [CancelToolTips](../mfc/reference/cwnd-class.md#canceltooltips), [FilterToolTipMessage](../mfc/reference/cwnd-class.md#filtertooltipmessage), und [OnToolHitTest ](../mfc/reference/cwnd-class.md#ontoolhittest). Finden Sie weitere Informationen darüber, wie sie QuickInfos implementieren diese individuelle Memberfunktionen aus.  
  
 Wenn Sie erstellen Sie eine Symbolleiste mit `CToolBarCtrl`, können Sie QuickInfos für die Symbolleiste, die direkt mit der folgenden Memberfunktionen implementieren: [GetToolTips](../mfc/reference/ctoolbarctrl-class.md#gettooltips) und [SetToolTips](../mfc/reference/ctoolbarctrl-class.md#settooltips). Finden Sie unter diese einzelne Memberfunktionen und [Behandlung von Tool Tipp Benachrichtigungen](../mfc/handling-tool-tip-notifications.md) für Weitere Informationen darüber, wie sie QuickInfos implementieren.  
  
 Die `CToolTipCtrl` Klasse stellt die Funktionalität des allgemeinen Windows-Tool QuickInfo-Steuerelements bereit. Ein einzelnes QuickInfo-Steuerelement kann es sich um Informationen für mehrere Tools bereitstellen. Ein Tool ist ein Fenster, z. B. ein untergeordnetes Fenster oder Steuerelement oder einen anwendungsdefinierten rechteckigen Bereich im Clientbereich eines Fensters. Die [CMFCToolTipCtrl](../mfc/reference/cmfctooltipctrl-class.md) Klasse leitet sich von `CToolTipCtrl` und bietet zusätzliche visuelle Stile und Funktionen.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CToolTipCtrl](../mfc/using-ctooltipctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)


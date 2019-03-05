---
title: Erstellen eines CToolBarCtrl-Objekts
ms.date: 11/04/2016
f1_keywords:
- CToolBarCtrl
helpviewer_keywords:
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: a4f6bf0c-0195-4dbf-a09e-aee503e19dc3
ms.openlocfilehash: d0f41731e3a4db7b15d4f2a7ebaac94135d5350d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265105"
---
# <a name="creating-a-ctoolbarctrl-object"></a>Erstellen eines CToolBarCtrl-Objekts

[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) Objekte enthalten mehrere interne Datenstrukturen – eine Liste von Bitmaps für Schaltflächen-Image, eine Liste der Schaltfläche Label-Zeichenfolgen und eine Liste der `TBBUTTON` Strukturen –, die ein Bild zuordnen und/oder die Zeichenfolge, die Position, Stil, State, und Befehls-ID der Schaltfläche. Jedes der Elemente für diese Datenstrukturen wird durch einen nullbasierten Index bezeichnet. Vor der Verwendung einer `CToolBarCtrl` Objekt ist, müssen Sie diese Datenstrukturen einrichten. Eine Liste der Datenstrukturen, finden Sie unter [Symbolleisten-Steuerelemente](controls-mfc.md) im Windows SDK. Die Liste der Zeichenfolgen kann nur für Symboltitel verwendet werden. Zeichenfolgen können über die Symbolleiste kann nicht abgerufen werden.

Verwenden einer `CToolBarCtrl` Objekt, Sie werden in der Regel gehen Sie folgendermaßen vor:

### <a name="to-use-a-ctoolbarctrl-object"></a>Verwenden ein CToolBarCtrl-Objekts

1. Erstellen der [CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md) Objekt.

1. Rufen Sie [erstellen](../mfc/reference/ctoolbarctrl-class.md#create) erstellen die allgemeine Windows-Symbolleisten-Steuerelement, und fügen Sie ihn auf die `CToolBarCtrl` Objekt. Wenn Sie Bitmapbilder für Schaltflächen möchten, können Sie die Bitmaps für Schaltflächen auf der Symbolleiste hinzufügen, durch den Aufruf [AddBitmap](../mfc/reference/ctoolbarctrl-class.md#addbitmap). Wenn Sie für Schaltflächen zeichenfolgenbezeichnungen möchten, können Sie die Zeichenfolgen auf der Symbolleiste hinzufügen, durch den Aufruf [AddString](../mfc/reference/ctoolbarctrl-class.md#addstring) und/oder [AddStrings](../mfc/reference/ctoolbarctrl-class.md#addstrings). Nach dem Aufruf `AddString` und/oder `AddStrings`, rufen Sie [AutoSize](../mfc/reference/ctoolbarctrl-class.md#autosize) um die Zeichenfolge oder Zeichenfolgen angezeigt werden, zu erhalten.

1. Fügen Sie der Symbolleiste durch Aufrufen von [AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons).

1. Behandeln Sie QuickInfos können **TTN_NEEDTEXT** Meldungen in der Symbolleiste des Fensters, siehe [behandeln Tool Tipp Benachrichtigungen](../mfc/handling-tool-tip-notifications.md).

1. Wenn Sie Ihre Benutzer zum Anpassen der Symbolleiste können soll, behandeln Anpassung von benachrichtigungsmeldungen in das besitzende Fenster wie in beschrieben [Behandeln von Anpassungsbenachrichtigungen](../mfc/handling-customization-notifications.md).

## <a name="see-also"></a>Siehe auch

[Verwenden von CToolBarCtrl](../mfc/using-ctoolbarctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

---
title: Erstellen eines CToolBarCtrl-Objekts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CToolBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- toolbar controls [MFC], creating
- CToolBarCtrl class [MFC], creating toolbars
ms.assetid: a4f6bf0c-0195-4dbf-a09e-aee503e19dc3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c98f99ef7ff26fed7d7df89881d2148af6bc993a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421647"
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


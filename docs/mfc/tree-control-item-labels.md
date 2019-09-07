---
title: Elementbezeichnungen in Struktursteuerelementen
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], item labels
- labels, CTreeCtrl items
- CTreeCtrl class [MFC], item labels
- item labels, tree controls
- item labels
ms.assetid: fe834107-1a25-4280-aced-774c11565805
ms.openlocfilehash: 16bb2bbe63eaf8ea4ce30040589d4a8a4cf4dfd3
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70741463"
---
# <a name="tree-control-item-labels"></a>Elementbezeichnungen in Struktursteuerelementen

Sie geben in der Regel den Text der Bezeichnung eines Elements an, wenn Sie das Element dem Struktur Steuerelement hinzufügen ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)). Die `InsertItem` Member-Funktion kann eine [tvitem](/windows/win32/api/commctrl/ns-commctrl-tvitemw) -Struktur übergeben, die die Eigenschaften des Elements definiert, einschließlich einer Zeichenfolge, die den Text der Bezeichnung enthält. `InsertItem`verfügt über mehrere über Ladungen, die mit verschiedenen Kombinationen von Parametern aufgerufen werden können.

Ein Struktur Steuerelement ordnet Speicher zum Speichern der einzelnen Elemente zu. der Text der Element Bezeichnungen nimmt einen signifikanten Teil dieses Speichers an. Wenn Ihre Anwendung eine Kopie der Zeichen folgen im Struktur Steuerelement beibehält, können Sie die Arbeitsspeicher Anforderungen des Steuer Elements verringern, indem Sie den **LPSTR_TEXTCALLBACK** -Wert im *pszText* -Member von `TV_ITEM` oder das *lpszitem* -Element angeben. , anstatt tatsächliche Zeichen folgen an das Struktur Steuerelement zu übergeben. Die Verwendung von **LPSTR_TEXTCALLBACK** bewirkt, dass das Struktur Steuerelement den Text der Bezeichnung eines Elements von der Anwendung abruft, wenn das Element neu gezeichnet werden muss. Zum Abrufen des Texts sendet das Struktur Steuerelement eine [TVN_GETDISPINFO](/windows/win32/Controls/tvn-getdispinfo) -Benachrichtigungs Meldung, die die Adresse einer [NMTVDISPINFO](/windows/win32/api/commctrl/ns-commctrl-nmtvdispinfow) -Struktur enthält. Sie müssen Antworten, indem Sie die entsprechenden Member der enthaltenen Struktur festlegen.

Ein Struktur Steuerelement verwendet Arbeitsspeicher, der vom Heap des Prozesses belegt wird, der das Struktur Steuerelement erstellt. Die maximale Anzahl von Elementen in einem Struktur Steuerelement basiert auf der Menge an Arbeitsspeicher, die im Heap verfügbar ist. Jedes Element benötigt 64 Bytes.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

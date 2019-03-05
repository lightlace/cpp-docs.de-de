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
ms.openlocfilehash: c945556ff9236db1ca61b15f1072efdc2f49541f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57278885"
---
# <a name="tree-control-item-labels"></a>Elementbezeichnungen in Struktursteuerelementen

Der Text, der die Bezeichnung eines Elements wird in der Regel angeben, wenn Sie das Element das Strukturansicht-Steuerelement hinzufügen ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)). Die `InsertItem` kann Member-Funktion übergeben, eine [TVITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtvitema) Struktur, die die Eigenschaften des Elements, einschließlich der Zeichenfolge mit dem Text der Bezeichnung definiert. `InsertItem` verfügt über mehrere Überladungen, die mit verschiedenen Kombinationen von Parametern aufgerufen werden kann.

Ein Strukturansicht-Steuerelement weist Speichern jedes Element Speicher; der Text, der den Elementnamen beansprucht einen großen Teil dieser Arbeitsspeicher ab. Wenn Ihre Anwendung eine Kopie der Zeichenfolgen in der Strukturansicht verwaltet, können Sie die arbeitsspeicheranforderungen für das Steuerelement verringern, durch Angabe der **LPSTR_TEXTCALLBACK** Wert in der *PszText* Mitglied `TV_ITEM` oder *LpszItem* Parameter anstelle der Übergabe der eigentlichen Zeichenfolgen, die dem Strukturansicht-Steuerelement. Mithilfe von **LPSTR_TEXTCALLBACK** bewirkt, dass das Strukturansicht-Steuerelement den Text, der die Bezeichnung eines Elements aus der Anwendung abrufen, wenn das Element neu gezeichnet werden muss. Zum Abrufen des Texts, sendet das Strukturansicht-Steuerelement eine [TVN_GETDISPINFO](/windows/desktop/Controls/tvn-getdispinfo) -benachrichtigungsmeldung und enthält die Adresse einer [NMTVDISPINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtvdispinfoa) Struktur. Sie müssen reagieren, durch Festlegen der entsprechenden Member der Struktur enthalten.

Ein Strukturansicht-Steuerelement verwendet die Speichermenge, die aus dem Heap des Prozesses, der den Strukturansicht-Steuerelement erstellt. Die maximale Anzahl von Elementen in einem Strukturansicht-Steuerelement basiert auf der Menge an Arbeitsspeicher im Heap verfügbar. Jedes Element hat 64 Bytes.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

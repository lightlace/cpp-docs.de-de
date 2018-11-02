---
title: Registerkarten und Attribute von Registerkarten-Steuerelementen
ms.date: 11/04/2016
helpviewer_keywords:
- attributes [MFC], reference topics
- tab controls [MFC], attributes
- tabs [MFC]
- tabs [MFC], attributes
- CTabCtrl class [MFC], tab control attributes
ms.assetid: ecf190cb-f323-4751-bfdb-766dbe6bb553
ms.openlocfilehash: ba63fdca32af28d0763dd4cf2da3465a99ddeb1f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571989"
---
# <a name="tabs-and-tab-control-attributes"></a>Registerkarten und Attribute von Registerkarten-Steuerelementen

Sie haben viel Kontrolle über das Aussehen und Verhalten von Registerkarten, aus denen ein Registerkarten-Steuerelement ([CTabCtrl](../mfc/reference/ctabctrl-class.md)). Jede Registerkarte kann es sich um eine Bezeichnung, ein Symbol, ein Zustand und eine anwendungsdefinierte 32-Bit-Wert zugeordnet werden. Für jede Registerkarte können Sie das Symbol, die Bezeichnung oder beides anzeigen.

Darüber hinaus kann jedes Registerelement haben drei mögliche Zustände: gedrückt oder nicht gedrückt hoveraktiviert hervorgehoben. Dieser Zustand kann nur festgelegt werden, durch Ändern eines vorhandenen Registerkartenelements. Zum Ändern eines vorhandenen Registerkartenelements Abrufen mit einem Aufruf von [GetItem](../mfc/reference/ctabctrl-class.md#getitem), Ändern der `TCITEM` Struktur (insbesondere die *dwState-Datenmember* und *den DwStateMask* -Datenmember ), und klicken Sie dann die geänderte zurückgeben `TCITEM` Struktur mit einem Aufruf von [SetItem](../mfc/reference/ctabctrl-class.md#setitem). Wenn Sie die Element-Zustände aller Elemente der Registerkarte in löschen müssen eine `CTabCtrl` Objekt, rufen Sie [DeselectAll](../mfc/reference/ctabctrl-class.md#deselectall). Diese Funktion setzt den Status aller Registerkartenelemente "oder" alle Elemente mit Ausnahme des derzeit ausgewählten zurück.

Der folgende Code löscht den Zustand aller Elemente der Registerkarte und anschließend wird den Status des dritten Elements geändert:

[!code-cpp[NVC_MFCControlLadenDialog#32](../mfc/codesnippet/cpp/tabs-and-tab-control-attributes_1.cpp)]

Weitere Informationen über Attribute von Registerkarten finden Sie unter [Registerkarten und Attribute von Registerkarten](/windows/desktop/Controls/tab-controls) im Windows SDK. Weitere Informationen zum Hinzufügen von Registerkarten zum Registerkarten-Steuerelement finden Sie unter [Hinzufügen von Registerkarten zum Registersteuerelement](../mfc/adding-tabs-to-a-tab-control.md) weiter unten in diesem Thema.

## <a name="see-also"></a>Siehe auch

[Verwenden von CTabCtrl](../mfc/using-ctabctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)


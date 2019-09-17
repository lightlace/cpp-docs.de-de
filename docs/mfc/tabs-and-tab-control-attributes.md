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
ms.openlocfilehash: 982ec40e330e2a7dda5c125d83e54751cd14416d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511245"
---
# <a name="tabs-and-tab-control-attributes"></a>Registerkarten und Attribute von Registerkarten-Steuerelementen

Sie haben eine beträchtliche Kontrolle über das Aussehen und Verhalten von Registerkarten, die ein Registerkarten-Steuerelement ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) bilden. Jede Registerkarte kann eine Bezeichnung, ein Symbol, einen Element Zustand und einen Anwendungs definierten 32-Bit-Wert aufweisen. Für jede Registerkarte können Sie das Symbol, die Bezeichnung oder beides anzeigen.

Darüber hinaus kann jedes Registerkarten Element drei mögliche Zustände aufweisen: gedrückt, nicht gedrückt oder hervorgehoben. Dieser Status kann nur festgelegt werden, indem ein vorhandenes Registerkarten Element geändert wird. Wenn Sie ein vorhandenes Registerkartenelement ändern möchten, rufen Sie es mit einem Aufruf von [GetItem](../mfc/reference/ctabctrl-class.md#getitem) ab, bearbeiten Sie die `TCITEM`-Struktur (insbesondere die Datenmember *dwState* und *dwStateMask*), und geben Sie die bearbeitete `TCITEM`-Struktur mit einem Aufruf von [SetItem](../mfc/reference/ctabctrl-class.md#setitem) zurück. Wenn Sie die Elementzustände aller Registerkartenelemente in einem `CTabCtrl`-Objekt löschen müssen, rufen Sie [DeselectAll](../mfc/reference/ctabctrl-class.md#deselectall) auf. Diese Funktion setzt den Status aller Tabstopp Elemente oder aller Elemente außer der aktuell ausgewählten Elemente zurück.

Der folgende Code löscht den Status aller Registerkarten Elemente und ändert dann den Zustand des dritten Elements:

[!code-cpp[NVC_MFCControlLadenDialog#32](../mfc/codesnippet/cpp/tabs-and-tab-control-attributes_1.cpp)]

Weitere Informationen über Registerkarten Attribute finden Sie unter [Registerkarten und Registerkarten Attribute](/windows/win32/Controls/tab-controls) in der Windows SDK. Weitere Informationen zum Hinzufügen von Registerkarten zu einem Registerkarten-Steuerelement finden Sie unter [Hinzufügen von Registerkarten zu einem Registerkarten-Steuer](../mfc/adding-tabs-to-a-tab-control.md) Element weiter unten

## <a name="see-also"></a>Siehe auch

[Verwenden von CTabCtrl](../mfc/using-ctabctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

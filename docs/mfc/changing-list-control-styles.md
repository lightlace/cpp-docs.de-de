---
title: Ändern der Stile von Listensteuerelementen
ms.date: 11/04/2016
helpviewer_keywords:
- styles [MFC], CListCtrl
- CListCtrl class [MFC], styles
- CListCtrl class [MFC], changing styles
ms.assetid: be74a005-0795-417c-9056-f6342aa74b26
ms.openlocfilehash: 2ba9ae81f7b1693be0df3565256a65e4e3561fd3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57266873"
---
# <a name="changing-list-control-styles"></a>Ändern der Stile von Listensteuerelementen

Sie können ändern, dass den Fensterstil eines Listensteuerelements ([CListCtrl](../mfc/reference/clistctrl-class.md)) zu einem beliebigen Zeitpunkt nach Abschluss des Erstellungsvorgangs. Ändern Sie den Fensterstil, ändern Sie die Art der Ansicht, die das Steuerelement verwendet. Z. B. um den Explorer zu emulieren, Sie möglicherweise angeben Menüelemente und Symbolleisten-Schaltflächen des Steuerelements zwischen verschiedenen Ansichten zu wechseln: Symbolansicht, Listenansicht und So weiter.

Angenommen, wenn der Benutzer das Menüelement auswählt, Sie konnten, einen Aufruf von [GetWindowLong](/windows/desktop/api/winuser/nf-winuser-getwindowlonga) den aktuellen Stil des Steuerelements abzurufen, und rufen Sie anschließend [SetWindowLong](/windows/desktop/api/winuser/nf-winuser-setwindowlonga) der Stil. Weitere Informationen finden Sie unter [Listenansicht-Steuerelemente mithilfe von](/windows/desktop/Controls/using-list-view-controls) im Windows SDK.

Verfügbaren Formate finden Sie in [erstellen](../mfc/reference/clistctrl-class.md#create). Die Stile **LVS_ICON**, **LVS_SMALLICON**, **LVS_LIST**, und **LVS_REPORT** die vier Listenansichten des Steuerelements festlegen.

## <a name="extended-styles"></a>Erweiterte Stile

Zusätzlich zu den Standardformaten für ein Listensteuerelement gibt es eine andere Gruppe, die als "Erweiterte Stile" bezeichnet. Diese Formate werden [erweiterte Listenansicht-Formatvorlagen](/windows/desktop/Controls/extended-list-view-styles) im Windows SDK bieten eine Vielzahl von nützlichen Features, die das Verhalten des Listensteuerelements anpassen. Um das Verhalten eines bestimmten Formats (wie z. B. Hover-Auswahl) zu implementieren, stellen Sie einen Aufruf von [wird CListCtrl:: SetExtendedStyle](../mfc/reference/clistctrl-class.md#setextendedstyle), übergeben das erforderliche Format. Das folgende Beispiel zeigt den Funktionsaufruf an:

[!code-cpp[NVC_MFCControlLadenDialog#22](../mfc/codesnippet/cpp/changing-list-control-styles_1.cpp)]

> [!NOTE]
>  Zeigen Sie die Auswahl funktioniert, auch benötigen Sie entweder **Wenn zusätzlich LVS_EX_ONECLICKACTIVATE** oder **LVS_EX_TWOCLICKACTIVATE gesetzt** aktiviert.

## <a name="see-also"></a>Siehe auch

[Verwenden von CListCtrl](../mfc/using-clistctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

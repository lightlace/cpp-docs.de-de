---
title: Verwenden einer Dialogleiste mit einem Grundleisten-Steuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- WS_EX_TRANSPARENT style
- rebar controls [MFC], dialog bars
- dialog bars [MFC], using with rebar bands
ms.assetid: e528cea0-6b81-4bdf-9643-7c03b6176590
ms.openlocfilehash: e4e786d3670ec74b734739e29aa7e3e33b5af384
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302366"
---
# <a name="using-a-dialog-bar-with-a-rebar-control"></a>Verwenden einer Dialogleiste mit einem Grundleisten-Steuerelement

Wie in den Grund leisten [-Steuerelementen und-Bändern](../mfc/rebar-controls-and-bands.md)erwähnt, kann jedes Band nur ein untergeordnetes Fenster (oder Steuerelement) enthalten. Dies kann eine Einschränkung sein, wenn Sie mehr als ein untergeordnetes Fenster pro Band haben möchten. Eine bequeme Problem Umgehung ist das Erstellen einer Dialog leisten Ressource mit mehreren Steuerelementen und das anschließende Hinzufügen eines Info leisten-Bands (das die Dialog Leiste enthält) zum Info leisten-Steuerelement.

Wenn Sie möchten, dass das Dialogfeld leisten-Band transparent erscheint, legen Sie den WS_EX_TRANSPARENT erweiterten Stil für das Dialog leisten Objekt fest. Da WS_EX_TRANSPARENT jedoch einige Probleme beim ordnungsgemäßen Zeichnen des Hintergrunds einer Dialog Leiste hat, müssen Sie etwas zusätzlicher arbeiten, um den gewünschten Effekt zu erzielen.

Im folgenden Verfahren werden die erforderlichen Schritte zum Erreichen von Transparenz ohne Verwendung des erweiterten WS_EX_TRANSPARENT erweitert.

### <a name="to-implement-a-transparent-dialog-bar-in-a-rebar-band"></a>So implementieren Sie eine transparente Dialog Leiste in einem Info leisten Band

1. Fügen Sie im [Dialogfeld Klasse hinzufügen](../mfc/reference/adding-an-mfc-class.md)eine neue Klasse hinzu (z. b. `CMyDlgBar`), die das Dialog leisten Objekt implementiert.

1. Fügen Sie einen Handler für die WM_ERASEBKGND Nachricht hinzu.

1. Ändern Sie im neuen Handler den vorhandenen Code entsprechend dem folgenden Beispiel:

   [!code-cpp[NVC_MFCControlLadenDialog#29](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_1.cpp)]

1. Fügen Sie einen Handler für die WM_MOVE Nachricht hinzu.

1. Ändern Sie im neuen Handler den vorhandenen Code entsprechend dem folgenden Beispiel:

   [!code-cpp[NVC_MFCControlLadenDialog#30](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_2.cpp)]

Die neuen Handler simulieren die Transparenz der Dialog Leiste, indem Sie die WM_ERASEBKGND Meldung an das übergeordnete Fenster weiterleiten und jedes Mal, wenn das Dialog leisten Objekt verschoben wird, ein Repaint erzwingen.

## <a name="see-also"></a>Siehe auch

[Verwenden von CReBarCtrl](../mfc/using-crebarctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

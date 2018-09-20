---
title: Grundleisten-Steuerelemente und Bänder | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rebar controls [MFC], working with bands in
- bands, in rebar controls
ms.assetid: b647e7a5-9ea7-48b1-8e5f-096d104748f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 988b16bb58462b42b8d4412a821cfc3fac5b4878
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443981"
---
# <a name="rebar-controls-and-bands"></a>Grundleisten-Steuerelemente und Bänder

Der Hauptzweck eines Grundleisten-Steuerelements ist, fungiert als Container für untergeordnete Fenster, gemeinsame Dialogfeld-Steuerelemente, Menüs, Symbolleisten und So weiter. Diese Beschränkung wird durch das Konzept eines "Bandes." unterstützt. Jede Infoleistenband kann eine beliebige Kombination von eine Ziehpunktleiste, eine Bitmap, einer textbezeichnung und einem untergeordneten Fenster enthalten.

Klasse `CReBarCtrl` bietet viele Memberfunktionen, Sie verwenden, um abzurufen und zu bearbeiten, müssen die Informationen für ein bestimmtes Infoleistenband können:

- [GetBandCount](../mfc/reference/crebarctrl-class.md#getbandcount) Ruft die Anzahl der aktuellen Bänder in der Grundleisten-Steuerelement ab.

- [GetBandInfo](../mfc/reference/crebarctrl-class.md#getbandinfo) initialisiert einen **REBARBANDINFO** Struktur mit Informationen aus dem angegebenen Band. Es wird eine entsprechende [SetBandInfo](../mfc/reference/crebarctrl-class.md#setbandinfo) Member-Funktion.

- [GetRect](../mfc/reference/crebarctrl-class.md#getrect) Ruft das umschließende Rechteck des angegebenen Bandes.

- [GetRowCount](../mfc/reference/crebarctrl-class.md#getrowcount) Ruft die Anzahl von Band Zeilen in einem Grundleisten-Steuerelement ab.

- [IDToIndex](../mfc/reference/crebarctrl-class.md#idtoindex) Ruft den Index eines angegebenen Bandes ab.

- [GetBandBorders](../mfc/reference/crebarctrl-class.md#getbandborders) Ruft ab, die Rahmen eines Bandes.

Zusätzlich zur Bearbeitung stehen mehrere Memberfunktionen, die Sie für bestimmte rebarbereichen ausgeführt werden können.

[InsertBand](../mfc/reference/crebarctrl-class.md#insertband) und [DeleteBand](../mfc/reference/crebarctrl-class.md#deleteband) hinzufügen und Entfernen von rebarbereichen. [MinimizeBand](../mfc/reference/crebarctrl-class.md#minimizeband) und [MaximizeBand](../mfc/reference/crebarctrl-class.md#maximizeband) Auswirkungen auf die aktuelle Größe der ein bestimmtes Infoleistenband. [MoveBand](../mfc/reference/crebarctrl-class.md#moveband) ändert sich der Index von einem bestimmten Infoleistenband. [ShowBand](../mfc/reference/crebarctrl-class.md#showband) Blendet oder ein Infoleistenband des Benutzers.

Das folgende Beispiel zeigt eine Symbolleistenband hinzufügen (*M_wndToolBar*) auf ein vorhandenes Grundleistensteuerelement (*M_wndReBar*). Das Band wird beschrieben, mit der Initialisierung der `rbi` Struktur und dem anschließenden Aufrufen der `InsertBand` Memberfunktion:

[!code-cpp[NVC_MFCControlLadenDialog#27](../mfc/codesnippet/cpp/rebar-controls-and-bands_1.cpp)]

## <a name="see-also"></a>Siehe auch

[Verwenden von CReBarCtrl](../mfc/using-crebarctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)


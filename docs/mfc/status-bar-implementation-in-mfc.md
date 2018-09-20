---
title: Implementieren der Statusleiste in MFC | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- COldStatusBar
dev_langs:
- C++
helpviewer_keywords:
- status bars [MFC], implementing in MFC
- CStatusBarCtrl class [MFC], and MFC status bars
- CStatusBar class [MFC], and CStatusBarCtrl class [MFC]
- CStatusBarCtrl class [MFC], and CStatusBar class [MFC]
- status bars [MFC], backward compatibility
- status bars [MFC], old with COldStatusBar class [MFC]
- COldStatusBar class [MFC]
- status bars [MFC], and CStatusBarCtrl class
- CStatusBar class [MFC], and MFC status bars
- status indicators
- status bars [MFC], Windows 95 implementation
ms.assetid: be5cd876-38e3-4d5c-b8cb-16d57a16a142
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e593227daabb2d2c25d593cfb58ef23ba7855be7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436714"
---
# <a name="status-bar-implementation-in-mfc"></a>Implementieren der Statusleiste mit MFC

Ein [CStatusBar](../mfc/reference/cstatusbar-class.md) Objekt ist eine Steuerleiste mit einer Zeile von Textausgabebereichen. Die Ausgabebereiche werden häufig als Nachricht Zeilen und Statusindikatoren verwendet. Beispiele sind im Menü hilfemeldung Zeilen, die der ausgewählten Menübefehls kurz erläutert wird und die Indikatoren, die den Status des Rollen-Taste, NUM- und andere Product Keys anzuzeigen.

Ab MFC 4.0, Statusleisten werden durch-Klasse implementiert [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md), die eine Statusleiste Standardsteuerelements kapselt. Für die Abwärtskompatibilität behält MFC die ältere Status Befehlsleisten-Standardimplementierung in Klasse `COldStatusBar`. Die Dokumentation für frühere Versionen von MFC beschreibt `COldStatusBar` unter `CStatusBar`.

[GetStatusBarCtrl](../mfc/reference/cstatusbar-class.md#getstatusbarctrl), eine Memberfunktion neue MFC 4.0, können Sie das allgemeine Windows-Steuerelement-Unterstützung für die Statusleiste anpassen und zusätzliche Funktionen nutzen. `CStatusBar` Member-Funktionen bieten Ihnen die meisten Funktionen der allgemeinen Windows-Steuerelemente; Wenn Sie jedoch aufrufen, `GetStatusBarCtrl`, Sie können den Statusleisten erteilen, sogar noch mehr Merkmale der Statusleiste. Beim Aufruf `GetStatusBarCtrl`, es gibt einen Verweis auf eine `CStatusBarCtrl` Objekt. Sie können diesen Verweis verwenden, das StatusBar-Steuerelement zu bearbeiten.

Die folgende Abbildung zeigt eine Statusleiste, in dem mehrere Indikatoren angezeigt.

![Statusleiste](../mfc/media/vc37dy1.gif "vc37dy1") eine Statusleiste

Wie die Symbolleiste wird das Objekt mit der Statusleiste in seiner übergeordneten Rahmenfensters eingebettet ist, und wird automatisch erstellt, wenn das Rahmenfenster erstellt wird. Die Statusleiste, wie alle Steuerleisten, automatisch auch zerstört, wenn der übergeordneten Frame zerstört wird.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Aktualisieren des Textes einen Statusleistenbereich](../mfc/updating-the-text-of-a-status-bar-pane.md)

- MFC-Klassen [CStatusBar](../mfc/reference/cstatusbar-class.md) und [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)

- [Steuerleisten](../mfc/control-bars.md)

- [Dialogleisten](../mfc/dialog-bars.md)

- [Symbolleisten (MFC-Symbolleisten-Implementierung)](../mfc/mfc-toolbar-implementation.md)

## <a name="see-also"></a>Siehe auch

[Statusleisten](../mfc/status-bars.md)


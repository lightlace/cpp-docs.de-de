---
title: Implementieren der Statusleiste mit MFC
ms.date: 11/04/2016
f1_keywords:
- COldStatusBar
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
ms.openlocfilehash: 25848e4467a0d767c40ffb00a1bd4d50a062d3a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50496278"
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


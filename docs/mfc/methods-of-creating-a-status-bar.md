---
title: Methoden zum Erstellen einer Statusleiste
ms.date: 11/04/2016
helpviewer_keywords:
- CStatusBar class [MFC], vs. CStatusBarCtrl
- methods [MFC], creating status bars
- CStatusBarCtrl class [MFC], vs. CStatusBar
- CStatusBarCtrl class [MFC], creating
- methods [MFC]
- status bars [MFC], creating
ms.assetid: 9aeaf290-7099-4762-a5ba-9c26705333c9
ms.openlocfilehash: a2301301d0012bd93ffedd0452dec140174402e0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383874"
---
# <a name="methods-of-creating-a-status-bar"></a>Methoden zum Erstellen einer Statusleiste

MFC bietet zwei Klassen zum Erstellen von Statusleisten: [CStatusBar](../mfc/reference/cstatusbar-class.md) und [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) (die dient als Wrapper für die allgemeine Windows-Steuerungs-API). `CStatusBar` bietet alle Funktionen der Statusleiste Standardsteuerelements, er automatisch interagiert mit Menüs und Symbolleisten, und viele der erforderlichen steuerelementeinstellungen für allgemeine und Strukturen für Sie; verarbeitet die resultierende ausführbare Datei in der Regel werden jedoch größer ist als mit erstellt `CStatusBarCtrl`.

`CStatusBarCtrl` Ergebnisse in eine kleinere ausführbare Datei, und Sie können in der Regel lieber mit `CStatusBarCtrl` , wenn Sie nicht beabsichtigen, die die Statusleiste in die MFC-Architektur integriert. Wenn Sie planen, verwenden Sie `CStatusBarCtrl` und die Statusleiste in der MFC-Architektur integriert, Sie müssen zusätzliche Sorgfalt Statusleisten-Steuerelement Manipulationen mit MFC zu kommunizieren. Diese Kommunikation ist nicht schwierig. Es ist jedoch zusätzliche Arbeit, die nicht benötigten ist bei Verwendung von `CStatusBar`.

Visual C++ bietet zwei Möglichkeiten, um das allgemeine StatusBar-Steuerelement nutzen.

- Erstellen Sie die Statusleiste mit `CStatusBar`, und rufen dann [GetStatusBarCtrl](../mfc/reference/cstatusbar-class.md#getstatusbarctrl) für den Zugriff auf die `CStatusBarCtrl` Memberfunktionen.

- Erstellen Sie die Statusleiste mit [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)Konstruktor.

Beide Methoden erhalten Sie Zugriff auf die Memberfunktionen der das StatusBar-Steuerelement. Beim Aufruf `CStatusBar::GetStatusBarCtrl`, es gibt einen Verweis auf eine `CStatusBarCtrl` Objekt, damit Sie beide Sätze von Memberfunktionen verwenden können. Finden Sie unter [CStatusBar](../mfc/reference/cstatusbar-class.md) für Informationen zum Erstellen, und erstellen eine Statusleiste mit `CStatusBar`.

## <a name="see-also"></a>Siehe auch

[Verwenden von CStatusBarCtrl](../mfc/using-cstatusbarctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

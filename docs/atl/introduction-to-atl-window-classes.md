---
title: Einführung in ATL-Fensterklassen
ms.date: 11/04/2016
helpviewer_keywords:
- window classes
ms.assetid: 503efc2c-a269-495d-97cf-3fb300d52f3d
ms.openlocfilehash: 0c3bc70b5edfb089a6276003625b876d8c553dcb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62250479"
---
# <a name="introduction-to-atl-window-classes"></a>Einführung in ATL-Fensterklassen

Die folgenden ATL-Klassen dienen Windows zu implementieren:

- [CWindow](../atl/reference/cwindow-class.md) ermöglicht es Ihnen, fügen Sie ein Fensterhandle für die `CWindow` Objekt. Rufen Sie dann `CWindow` Methoden zum Ändern des Fensters.

- [CWindowImpl](../atl/reference/cwindowimpl-class.md) können Sie ein neues Fenster zu implementieren und Verarbeiten von Nachrichten mit einer meldungszuordnung. Sie erstellen ein Fenster auf der Grundlage einer neuen Windows-Klasse, übergeordnete Klasse einer vorhandenen Klasse oder Unterklasse eines vorhandenen Fensters.

- [CDialogImpl](../atl/reference/cdialogimpl-class.md) können Sie ein modales oder ein nicht modales Dialogfeld im Feld und Verarbeiten von Nachrichten mit einer meldungszuordnung implementieren.

- [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) ist eine vordefinierte-Klasse, die ein Fenster, dessen meldungszuordnung enthalten ist, in einer anderen Klasse implementiert. Mithilfe von `CContainedWindowT` ermöglicht es Ihnen, die Verarbeitung von Nachrichten in einer Klasse zu zentralisieren.

- [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) können Sie ein Dialogfeld (gebunden oder ungebunden) zu implementieren, die ActiveX-Steuerelemente hostet.

- [CSimpleDialog](../atl/reference/csimpledialog-class.md) können Sie ein modales Dialogfeld mit grundlegender Funktionalität zu implementieren.

- [CAxWindow](../atl/reference/caxwindow-class.md) können Sie ein Fenster zu implementieren, der ein ActiveX-Steuerelement hostet.

- [CAxWindow2T](../atl/reference/caxwindow2t-class.md) können Sie ein Fenster zu implementieren, die ein lizenziertes ActiveX-Steuerelement hostet.

Zusätzlich zu bestimmten Fensterklassen bietet ATL mehrere Klassen, die die Implementierung eines Objekts der ATL-Fenster zu vereinfachen. Dies sind:

- [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) verwaltet die Informationen eine neue Windows-Klasse.

- [CWinTraits](../atl/reference/cwintraits-class.md) und [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) bieten eine einfache Methode für die Standardisierung der Merkmale eines ATL-Fenster-Objekts.

## <a name="see-also"></a>Siehe auch

[Fensterklassen](../atl/atl-window-classes.md)

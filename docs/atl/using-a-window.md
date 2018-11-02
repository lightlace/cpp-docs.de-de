---
title: Verwenden ein Fenster (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- CWindow class, about CWindow class
- windows [C++], ATL
ms.assetid: b3b9cc8e-4287-486b-b080-38852bc2943a
ms.openlocfilehash: 7446196e9eec4b9d9236d4ab55afd9fcf859254b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568657"
---
# <a name="using-a-window"></a>Verwenden eines Fensters

Klasse [CWindow](../atl/reference/cwindow-class.md) können Sie ein Fenster zu verwenden. Nachdem Sie ein Fenster zum Anfügen einer `CWindow` Objekt, rufen Sie anschließend `CWindow` Methoden zum Ändern des Fensters. `CWindow` enthält auch einen HWND-Operator zum Konvertieren einer `CWindow` Objekt in ein HWND. Daher können Sie übergeben eine `CWindow` Objekt, das alle Funktionen, die ein Handle für ein Fenster ist erforderlich. Sie können ganz einfach kombinieren `CWindow` Methodenaufrufe und Win32-Funktionsaufrufe, ohne temporäre Objekte erstellen.

Da `CWindow` verfügt über nur zwei Member (ein Fensterhandle und die Standarddimensionen), es entstehen keine zusätzlichen Aufwand für Ihren Code. Darüber hinaus viele der `CWindow` Methoden einfach einen Wrapper für entsprechende Win32-API-Funktionen. Mithilfe von `CWindow`, das HWND-Element wird automatisch an die Win32-Funktion übergeben.

Zusätzlich zur Verwendung von `CWindow` direkt, Sie können auch aus dem Hinzufügen von Daten oder Code zu einer Klasse ableiten. ATL selbst abgeleitet wird, drei Klassen von `CWindow`: [CWindowImpl](../atl/implementing-a-window.md), [CDialogImpl](../atl/implementing-a-dialog-box.md), und [CContainedWindowT](../atl/using-contained-windows.md).

## <a name="see-also"></a>Siehe auch

[Fensterklassen](../atl/atl-window-classes.md)


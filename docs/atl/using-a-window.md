---
title: Mit einem Fenster (ATL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, windows
- CWindow class, about CWindow class
- windows [C++], ATL
ms.assetid: b3b9cc8e-4287-486b-b080-38852bc2943a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44b9988c0ecde4d0aee917fea686ec6511473318
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37847923"
---
# <a name="using-a-window"></a>Verwenden eines Fensters
Klasse [CWindow](../atl/reference/cwindow-class.md) können Sie ein Fenster zu verwenden. Nachdem Sie ein Fenster zum Anfügen einer `CWindow` Objekt, rufen Sie anschließend `CWindow` Methoden zum Ändern des Fensters. `CWindow` enthält auch einen HWND-Operator zum Konvertieren einer `CWindow` Objekt in ein HWND. Daher können Sie übergeben eine `CWindow` Objekt, das alle Funktionen, die ein Handle für ein Fenster ist erforderlich. Sie können ganz einfach kombinieren `CWindow` Methodenaufrufe und Win32-Funktionsaufrufe, ohne temporäre Objekte erstellen.  
  
 Da `CWindow` verfügt über nur zwei Member (ein Fensterhandle und die Standarddimensionen), es entstehen keine zusätzlichen Aufwand für Ihren Code. Darüber hinaus viele der `CWindow` Methoden einfach einen Wrapper für entsprechende Win32-API-Funktionen. Mithilfe von `CWindow`, das HWND-Element wird automatisch an die Win32-Funktion übergeben.  
  
 Zusätzlich zur Verwendung von `CWindow` direkt, Sie können auch aus dem Hinzufügen von Daten oder Code zu einer Klasse ableiten. ATL selbst abgeleitet wird, drei Klassen von `CWindow`: [CWindowImpl](../atl/implementing-a-window.md), [CDialogImpl](../atl/implementing-a-dialog-box.md), und [CContainedWindowT](../atl/using-contained-windows.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Fensterklassen](../atl/atl-window-classes.md)


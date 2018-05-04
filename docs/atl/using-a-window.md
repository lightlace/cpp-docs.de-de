---
title: In einem Fenster (ATL) | Microsoft Docs
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
ms.openlocfilehash: f946f99fd198db281418e2a471489b2236972435
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="using-a-window"></a>Verwenden ein Fenster
Klasse [CWindow](../atl/reference/cwindow-class.md) können Sie ein Fenster verwenden. Nachdem Sie ein Fenster zum Anfügen einer `CWindow` -Objekt, rufen Sie dann `CWindow` Methoden zum Ändern des Fensters. `CWindow` enthält auch eine `HWND` -Operator konvertiert einen `CWindow` -Objekt an eine `HWND`. Daher können Sie übergeben ein `CWindow` Objekt, das alle Funktionen, die ein Handle für ein Fenster ist erforderlich. Sie können problemlos kombinieren `CWindow` Methodenaufrufen und Win32-Funktionsaufrufe, ohne eine temporäre Objekte erstellen.  
  
 Da `CWindow` verfügt über nur zwei Member (ein Fensterhandle und die Standarddimensionen) unterscheiden sich ein Mehraufwand für Ihren Code. Darüber hinaus werden viele der `CWindow` Methoden umschließen lediglich die entsprechende Win32-API-Funktionen. Mithilfe von `CWindow`der `HWND` Member automatisch an die Win32-Funktion übergeben wird.  
  
 Zusätzlich zur Verwendung von `CWindow` direkt, Sie können auch zum Hinzufügen von Daten oder den Code zu Ihrer Klasse daraus ableiten. ATL selbst abgeleitet wird, drei Klassen von `CWindow`: [CWindowImpl](../atl/implementing-a-window.md), [CDialogImpl](../atl/implementing-a-dialog-box.md), und [CContainedWindow](../atl/using-contained-windows.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Fensterklassen](../atl/atl-window-classes.md)


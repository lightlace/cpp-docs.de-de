---
title: Fensterstile | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WS_MINIMIZEBOX
- WS_SIZEBOX
- WS_CLIPCHILDREN
- WS_TILED
- WS_GROUP
- WS_VSCROLL
- WS_CHILD
- WS_TABSTOP
- WS_HSCROLL
- WS_THICKFRAME
- WS_DISABLED
- WS_POPUP
- WS_ICONIC
- WS_MAXIMIZE
- WS_VISIBLE
- WS_POPUPWINDOW
- WS_TILEDWINDOW
- WS_DLGFRAME
- WS_MINIMIZE
- WS_CAPTION
- WS_OVERLAPPED
- WS_BORDER
- WS_MAXIMIZEBOX
- WS_OVERLAPPEDWINDOW
- WS_SYSMENU
- WS_CHILDWINDOW
- WS_CLIPSIBLINGS
dev_langs:
- C++
helpviewer_keywords:
- WS_THICKFRAME constant
- WS_TILEDWINDOW constant
- WS_MAXIMIZEBOX constant
- WS_DLGFRAME constant
- WS_CHILDWINDOW constant
- window styles, in MFC
- WS_CHILD constant
- WS_GROUP constant
- WS_MINIMIZE constant
- WS_CAPTION constant
- WS_MAXIMIZE constant
- WS_POPUP constant
- WS_SYSMENU constant
- WS_TILED constant
- window styles
- WS_POPUPWINDOW constant
- WS_CLIPSIBLINGS constant
- WS_BORDER constant
- WS_DISABLED constant
- WS_VSCROLL constant
- WS_OVERLAPPED constant
- WS_MINIMIZEBOX constant
- WS_VISIBLE constant
- WS_OVERLAPPEDWINDOW constant
- WS_TABSTOP constant
- WS_ICONIC constant
- WS_SIZEBOX constant
- WS_HSCROLL constant
- WS_CLIPCHILDREN constant
- styles, windows
ms.assetid: c85ffbe4-f4ff-4227-917a-48ec4a411842
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: d814e3a10132fb3fe88969ce434f8286b02afba5
ms.lasthandoff: 02/24/2017

---
# <a name="window-styles"></a>Fensterstile
-   `WS_BORDER`Erstellt ein Fenster mit einem Rahmen.  
  
-   **WS_CAPTION** erstellt ein Fenster mit einer Titelleiste (bedeutet den `WS_BORDER` Stil). Kann nicht verwendet werden, mit der **WS_DLGFRAME** Stil.  
  
-   **WS_CHILD** erstellt ein untergeordnetes Fenster. Kann nicht mit dem `WS_POPUP`-Stil verwendet werden.  
  
-   **WS_CHILDWINDOW** identisch mit der **WS_CHILD** Stil.  
  
-   **WS_CLIPCHILDREN** schließt den Bereich durch untergeordnete Fenster belegt wird, wenn Sie innerhalb des übergeordneten Fensters zeichnen. Wird verwendet, wenn Sie das übergeordnete Fenster erstellen.  
  
-   **WS_CLIPSIBLINGS** kappt untergeordnete Fenster relativ zueinander, d. h., wenn ein bestimmtes untergeordnetes Fenster eine Paint-Meldung empfängt die **WS_CLIPSIBLINGS** Stil Schneidet alle anderen überlappenden untergeordneten Fenster aus dem Bereich des zu aktualisierenden untergeordneten Fensters. (Wenn **WS_CLIPSIBLINGS** nicht angegeben und untergeordnete Fenster überlappen, wenn Sie im Clientbereich eines untergeordneten Fensters zeichnen, ist es möglich, im Clientbereich eines benachbarten untergeordneten Fensters zeichnen.) Für die Verwendung mit der **WS_CHILD** nur formatieren.  
  
-   **WS_DISABLED** erstellt ein Fenster, das anfänglich deaktiviert ist.  
  
-   **WS_DLGFRAME** erstellt ein Fenster mit einem doppelten Rahmen, aber ohne Titel.  
  
-   **WS_GROUP** gibt das erste Steuerelement einer Gruppe von Steuerelementen in der der Benutzer von einem Steuerelement zum nächsten mit den Pfeiltasten wechseln kann. Alle Steuerelemente, die mit definiert die **WS_GROUP** Stil **FALSE** nach das erste Steuerelement zur selben Gruppe gehören. Das nächste Steuerelement mit der **WS_GROUP** -Stil beginnt die nächste Gruppe (d. h. eine Gruppe endet, an dem die nächste beginnt).  
  
-   **WS_HSCROLL** erstellt ein Fenster mit einer horizontalen Bildlaufleiste.  
  
-   **WS_ICONIC** erstellt ein Fenster, das anfänglich minimiert ist. Identisch mit der **WS_MINIMIZE** Stil.  
  
-   **WS_MAXIMIZE** erstellt ein Fenster mit maximaler Größe.  
  
-   **WS_MAXIMIZEBOX** erstellt ein Fenster, das eine Maximierungsschaltfläche hat.  
  
-   **WS_MINIMIZE** erstellt ein Fenster, das anfänglich minimiert ist. Für die Verwendung mit der **WS_OVERLAPPED** nur formatieren.  
  
-   **WS_MINIMIZEBOX** erstellt ein Fenster, das eine Minimierungsschaltfläche hat.  
  
-   **WS_OVERLAPPED** erstellt ein überlappendes Fenster. Ein überlappende Fenster hat normalerweise eine Beschriftung und einen Rahmen.  
  
-   **WS_OVERLAPPEDWINDOW** erstellt ein überlappendes Fenster mit den **WS_OVERLAPPED**, **WS_CAPTION**, **WS_SYSMENU**, **WS_THICKFRAME**, **WS_MINIMIZEBOX**, und **WS_MAXIMIZEBOX** Formate.  
  
-   `WS_POPUP`Erstellt ein Popupfenster. Kann nicht verwendet werden, mit der **WS_CHILD** Stil.  
  
-   **WS_POPUPWINDOW** erstellt ein Popupfenster mit der `WS_BORDER`, `WS_POPUP`, und **WS_SYSMENU** Formate. Die **WS_CAPTION** Stil muss zusammen mit der **WS_POPUPWINDOW** Format, um das Systemmenü sichtbar zu machen.  
  
-   **WS_SIZEBOX** erstellt ein Fenster mit einem Rahmen. Identisch mit der **WS_THICKFRAME** Stil.  
  
-   **WS_SYSMENU** erstellt ein Fenster mit einem Systemmenüfeld in der Titelleiste. Nur zur Verwendung für Fenster mit Titelleisten.  
  
-   **WS_TABSTOP** gibt eine Reihe von Steuerelementen, die über die der Benutzer mithilfe der TAB-TASTE wechseln kann. Die TAB-Taste wechselt der Benutzer zum nächsten Steuerelement angegeben, indem die **WS_TABSTOP** Stil.  
  
-   **WS_THICKFRAME** erstellt ein Fenster mit einem breiten Rahmen, der zum Ändern der Fenstergröße verwendet werden kann.  
  
-   **WS_TILED** erstellt ein überlappendes Fenster. Ein überlappendes Fenster hat eine Titelleiste und einen Rahmen. Identisch mit der **WS_OVERLAPPED** Stil.  
  
-   **WS_TILEDWINDOW** erstellt ein überlappendes Fenster mit den **WS_OVERLAPPED**, **WS_CAPTION**, **WS_SYSMENU**, **WS_THICKFRAME**, **WS_MINIMIZEBOX**, und **WS_MAXIMIZEBOX** Formate. Identisch mit der **WS_OVERLAPPEDWINDOW** Stil.  
  
-   **WS_VISIBLE** erstellt ein Fenster, das anfänglich sichtbar ist.  
  
-   **WS_VSCROLL** erstellt ein Fenster mit einer vertikalen Bildlaufleiste.  
  
## <a name="see-also"></a>Siehe auch  
 [Von MFC verwendete Stile](../../mfc/reference/styles-used-by-mfc.md)   
 [CWnd:: Create](../../mfc/reference/cwnd-class.md#create)   
 [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex)   
 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)



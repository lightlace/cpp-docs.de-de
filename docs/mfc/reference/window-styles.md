---
title: "Fensterstile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WS_MINIMIZEBOX"
  - "WS_SIZEBOX"
  - "WS_CLIPCHILDREN"
  - "WS_TILED"
  - "WS_GROUP"
  - "WS_VSCROLL"
  - "WS_CHILD"
  - "WS_TABSTOP"
  - "WS_HSCROLL"
  - "WS_THICKFRAME"
  - "WS_DISABLED"
  - "WS_POPUP"
  - "WS_ICONIC"
  - "WS_MAXIMIZE"
  - "WS_VISIBLE"
  - "WS_POPUPWINDOW"
  - "WS_TILEDWINDOW"
  - "WS_DLGFRAME"
  - "WS_MINIMIZE"
  - "WS_CAPTION"
  - "WS_OVERLAPPED"
  - "WS_BORDER"
  - "WS_MAXIMIZEBOX"
  - "WS_OVERLAPPEDWINDOW"
  - "WS_SYSMENU"
  - "WS_CHILDWINDOW"
  - "WS_CLIPSIBLINGS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Stile, Fenster"
  - "Fensterstile"
  - "Fensterstile, in MFC"
  - "WS_BORDER-Konstante"
  - "WS_CAPTION-Konstante"
  - "WS_CHILD-Konstante"
  - "WS_CHILDWINDOW-Konstante"
  - "WS_CLIPCHILDREN-Konstante"
  - "WS_CLIPSIBLINGS-Konstante"
  - "WS_DISABLED-Konstante"
  - "WS_DLGFRAME-Konstante"
  - "WS_GROUP-Konstante"
  - "WS_HSCROLL-Konstante"
  - "WS_ICONIC-Konstante"
  - "WS_MAXIMIZE-Konstante"
  - "WS_MAXIMIZEBOX-Konstante"
  - "WS_MINIMIZE-Konstante"
  - "WS_MINIMIZEBOX-Konstante"
  - "WS_OVERLAPPED-Konstante"
  - "WS_OVERLAPPEDWINDOW-Konstante"
  - "WS_POPUP-Konstante"
  - "WS_POPUPWINDOW-Konstante"
  - "WS_SIZEBOX-Konstante"
  - "WS_SYSMENU-Konstante"
  - "WS_TABSTOP-Konstante"
  - "WS_THICKFRAME-Konstante"
  - "WS_TILED-Konstante"
  - "WS_TILEDWINDOW-Konstante"
  - "WS_VISIBLE-Konstante"
  - "WS_VSCROLL-Konstante"
ms.assetid: c85ffbe4-f4ff-4227-917a-48ec4a411842
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Fensterstile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   `WS_BORDER` Erstellt ein Fenster mit einem Rahmen.  
  
-   **WS\_CAPTION** Erstellt ein Fenster mit einer Titelleiste \(bedeutet den `WS_BORDER`\-Stil\).  Kann nicht mit dem **WS\_DLGFRAME**\-Stil verwendet werden.  
  
-   **WS\_CHILD** Erstellt ein untergeordnetes Fenster.  Kann nicht mit dem `WS_POPUP`\-Stil verwendet werden.  
  
-   **WS\_CHILDWINDOW** Identisch mit dem **WS\_CHILD**\-Stil.  
  
-   **WS\_CLIPCHILDREN** Schließt den Bereich aus, der durch untergeordnete Fenster belegt wird, wenn Sie innerhalb des übergeordneten Fensters zeichnen.  Wird verwendet, wenn Sie das übergeordnete Fenster erstellen.  
  
-   **WS\_CLIPSIBLINGS** Kappt untergeordnete Fenster relativ zueinander. Das heißt, wenn ein bestimmtes untergeordnetes Fenster eine paint\-Meldung empfängt, schneidet der **WS\_CLIPSIBLINGS**\-Stil alle anderen überlappenden untergeordneten Fenster aus dem Bereich des zu aktualisierenden untergeordneten Fensters aus. \(Wenn **WS\_CLIPSIBLINGS** nicht angegeben ist und untergeordnete Fenster überlappen, während Sie im Clientbereich eines untergeordneten Fensters zeichnen, es ist möglich, im Clientbereich eines benachbarten untergeordneten Fensters zu zeichnen.\) Nur zur Verwendung mit dem **WS\_CHILD**\-Stil.  
  
-   **WS\_DISABLED** Erstellt ein Fenster, das anfänglich deaktiviert ist.  
  
-   **WS\_DLGFRAME** Erstellt ein Fenster mit einem doppelten Rahmen, aber ohne Titel.  
  
-   **WS\_GROUP** Gibt das erste Steuerelement einer Gruppe von Steuerelementen an, in der ein Benutzer mit den Pfeiltasten von einem Steuerelement zum nächsten wechseln kann.  Alle Steuerelemente, die nach dem ersten Steuerelement mit dem **WS\_GROUP**\-Stil **FALSE** definiert wurden, gehören zu derselben Gruppe.  Mit dem nächsten Steuerelement im **WS\_GROUP**\-Stil beginnt die nächste Gruppe \(das heißt, eine Gruppe endet dort, wo die folgende beginnt\).  
  
-   **WS\_HSCROLL** Erstellt ein Fenster mit einer horizontalen Bildlaufleiste.  
  
-   **WS\_ICONIC** Erstellt ein Fenster, das anfänglich minimiert ist.  Identisch mit dem **WS\_MINIMIZE**\-Stil.  
  
-   **WS\_MAXIMIZE** Erstellt ein Fenster mit maximaler Größe.  
  
-   **WS\_MAXIMIZEBOX** Erstellt ein Fenster mit der Schaltfläche "Maximieren".  
  
-   **WS\_MINIMIZE** Erstellt ein Fenster, das anfänglich minimiert ist.  Nur zur Verwendung mit dem **WS\_OVERLAPPED**\-Stil.  
  
-   **WS\_MAXIMIZEBOX** Erstellt ein Fenster mit der Schaltfläche "Minimieren".  
  
-   **WS\_OVERLAPPED** Erstellt ein überlappendes Fenster.  Ein überlappende Fenster hat normalerweise eine Beschriftung und einen Rahmen.  
  
-   **WS\_OVERLAPPEDWINDOW** Erstellt ein überlappendes Fenster mit den Stilen **WS\_OVERLAPPED**, **WS\_CAPTION**, **WS\_SYSMENU**, **WS\_THICKFRAME**, **WS\_MINIMIZEBOX** und **WS\_MAXIMIZEBOX**.  
  
-   `WS_POPUP` Erstellt ein Popupfenster.  Kann nicht mit dem **WS\_CHILD**\-Stil verwendet werden.  
  
-   **WS\_POPUPWINDOW** Erstellt ein Popupfenster mit den Stilen `WS_BORDER`, `WS_POPUP` und **WS\_SYSMENU**.  Der **WS\_CAPTION**\-Stil muss mit dem **WS\_POPUPWINDOW**\-Stil kombiniert werden, um das Systemmenü sichtbar zu machen.  
  
-   **WS\_SIZEBOX** Erstellt ein Fenster mit einem Rahmen, dessen Größe angepasst werden kann.  Identisch mit dem **WS\_THICKFRAME**\-Stil.  
  
-   **WS\_SYSMENU** Erstellt ein Fenster mit einem Systemmenüfeld in der Titelleiste.  Nur zur Verwendung für Fenster mit Titelleisten.  
  
-   **WS\_TABSTOP** Gibt eines von beliebig vielen Steuerelementen an, zwischen denen der Benutzer mit der TAB\-TASTE wechseln kann.  Mit der TAB\-TASTE wechselt der Benutzer zum nächsten Steuerelement, das durch den **WS\_TABSTOP**\-Stil angegeben ist.  
  
-   **WS\_THICKFRAME** Erstellt ein Fenster mit einem breiten Rahmen, der zum Verändern der Fenstergröße verwendet werden kann.  
  
-   **WS\_TILED** Erstellt ein überlappendes Fenster.  Ein überlappendes Fenster hat eine Titelleiste und einen Rahmen.  Identisch mit dem **WS\_OVERLAPPED** \-Stil.  
  
-   **WS\_TILEDWINDOW** Erstellt ein überlappendes Fenster mit den Stilen **WS\_OVERLAPPED**, **WS\_CAPTION**, **WS\_SYSMENU**, **WS\_THICKFRAME**, **WS\_MINIMIZEBOX** und **WS\_MAXIMIZEBOX**.  Identisch mit dem **WS\_OVERLAPPEDWINDOW**\-Stil.  
  
-   **WS\_VISIBLE** Erstellt ein Fenster, das anfänglich sichtbar ist.  
  
-   **WS\_VSCROLL** Erstellt ein Fenster mit einer vertikalen Bildlaufleiste.  
  
## Siehe auch  
 [Von MFC verwendete Stile](../../mfc/reference/styles-used-by-mfc.md)   
 [CWnd::Create](../Topic/CWnd::Create.md)   
 [CWnd::CreateEx](../Topic/CWnd::CreateEx.md)   
 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)
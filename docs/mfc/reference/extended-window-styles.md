---
title: "Erweiterte Fensterstile"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "WS_EX_TOOLWINDOW"
  - "WS_EX_LEFTSCROLLBAR"
  - "WS_EX_RTLREADING"
  - "WS_EX_WINDOWEDGE"
  - "WS_EX_CLIENTEDGE"
  - "WS_EX_STATICEDGE"
  - "WS_EX_LTRREADING"
  - "WS_EX_DLGMODALFRAME"
  - "WS_EX_RIGHTSCROLLBAR"
  - "WS_EX_CONTROLPARENT"
  - "WS_EX_ACCEPTFILES"
  - "WS_EX_TRANSPARENT"
  - "WS_EX_RIGHT"
  - "WS_EX_APPWINDOW"
  - "WS_EX_TOPMOST"
  - "WS_EX_CONTEXTHELP"
  - "WS_EX_MDICHILD"
  - "WS_EX_LEFT"
  - "WS_EX_OVERLAPPEDWINDOW"
  - "WS_EX_PALETTEWINDOW"
  - "WS_EX_NOPARENTNOTIFY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Erweiterte Fensterstile"
  - "Stile, Fenster"
  - "WS_EX_ACCEPTFILES-Konstante"
  - "WS_EX_APPWINDOW-Konstante"
  - "WS_EX_CLIENTEDGE-Konstante"
  - "WS_EX_CONTEXTHELP-Konstante"
  - "WS_EX_CONTROLPARENT-Konstante"
  - "WS_EX_DLGMODALFRAME-Konstante"
  - "WS_EX_LEFT-Konstante"
  - "WS_EX_LEFTSCROLLBAR-Konstante"
  - "WS_EX_LTRREADING-Konstante"
  - "WS_EX_MDICHILD-Konstante"
  - "WS_EX_NOPARENTNOTIFY-Konstante"
  - "WS_EX_OVERLAPPEDWINDOW-Konstante"
  - "WS_EX_PALETTEWINDOW-Konstante"
  - "WS_EX_RIGHT-Konstante"
  - "WS_EX_RIGHTSCROLLBAR-Konstante"
  - "WS_EX_RTLREADING-Konstante"
  - "WS_EX_STATICEDGE-Konstante"
  - "WS_EX_TOOLWINDOW-Konstante"
  - "WS_EX_TOPMOST-Konstante"
  - "WS_EX_TRANSPARENT-Konstante"
  - "WS_EX_WINDOWEDGE-Konstante"
ms.assetid: d18e6c69-0a01-49ed-b58a-55b3802b47c1
caps.latest.revision: 14
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Erweiterte Fensterstile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   **WS\_EX\_ACCEPTFILES** Gibt an, dass ein Fenster, das in diesem Format erstellt wird, Drag & Drop\-Dateien akzeptiert.  
  
-   **WS\_EX\_APPWINDOW** Erzwingt, dass ein Fenster der obersten Ebene in der Taskleiste angezeigt wird, wenn das Fenster sichtbar ist.  
  
-   **WS\_EX\_CLIENTEDGE** Gibt an, dass ein Fenster in 3D dargestellt wird \- d. h. über einen Rahmen mit einem vertieften Rand verfügt.  
  
-   **WS\_EX\_CONTEXTHELP** Schließt ein Fragezeichen in der Titelleiste des Fensters ein.  Wenn der Benutzer auf das Fragezeichen klickt, wird der Cursor zu einem Fragezeichen geändert.  Wenn der Benutzer anschließend auf ein untergeordnetes Fenster klickt, empfängt das untergeordnete Fenster eine **WM\_HELP**\-Meldung.  
  
-   **WS\_EX\_CONTROLPARENT** Ermöglicht es dem Benutzer, mithilfe der TAB\-TASTE unter den untergeordneten Fenstern des Fensters zu navigieren.  
  
-   **WS\_EX\_DLGMODALFRAME** Bezeichnet ein Fenster mit einem doppelten Rahmen, das \(optional\) mit einer Titelleiste erstellt werden kann, wenn Sie das Formatflag **WS\_CAPTION** im `dwStyle`\-Parameter angeben.  
  
-   **WS\_EX\_LAYERED** Das Fenster ist ein [überlappendes Fenster](http://msdn.microsoft.com/library/ms632599\(v=vs.85\).aspx#layered").  Dieses Format kann nicht verwendet werden, wenn das Fenster das [Klassenformat](http://msdn.microsoft.com/library/ms633574\(v=vs.85\).aspx#class_styles")**CS\_OWNDC** oder **CS\_CLASSDC** hat.  [!INCLUDE[win8_first](../../mfc/reference/includes/win8_first_md.md)] unterstützt jedoch das Format **WS\_EX\_LAYERED** für untergeordnete Fenster, während frühere Windows\-Versionen es nur für Fenster der obersten Ebene unterstützt haben.  
  
-   **WS\_EX\_LEFT** Ordnet einem generischem Fenster die Eigenschaften "linksbündig" zu.  Dies ist der Standardwert.  
  
-   **WS\_EX\_LEFTSCROLLBAR** Platziert eine vertikale Bildlaufleiste auf der linken Seite des Clientbereichs.  
  
-   **WS\_EX\_LTRREADING** Zeigt den Fenstertext mit der Leserichtungseigenschaften "von links nach rechts" an.  Dies ist der Standardwert.  
  
-   **WS\_EX\_MDICHILD** Erstellt ein untergeordnetes MDI\-Fenster.  
  
-   **WS\_EX\_NOPARENTNOTIFY** Gibt an, dass ein untergeordnetes Fenster, das in diesem Format erstellt wird, die `WM_PARENTNOTIFY`\-Nachricht nicht an das übergeordnete Fenster sendet, wenn das untergeordnete Fenster erstellt oder beschädigt wird.  
  
-   **WS\_EX\_OVERLAPPEDWINDOW** Kombiniert die Formate **WS\_EX\_CLIENTEDGE** und **WS\_EX\_WINDOWEDGE**.  
  
-   **WS\_EX\_PALETTEWINDOW** Kombiniert die Formate **WS\_EX\_WINDOWEDGE** und **WS\_EX\_TOPMOST**.  
  
-   **WS\_EX\_RIGHT** Ordnet einem generischen Fenster die Eigenschaft "rechtsbündig" zu.  Dies hängt von der Fensterklasse ab.  
  
-   **WS\_EX\_RIGHTSCROLLBAR** Platziert eine vertikale Bildlaufleiste \(sofern vorhanden\) auf der rechten Seite des Clientbereichs.  Dies ist der Standardwert.  
  
-   **WS\_EX\_RTLREADING** Zeigt den Fenstertext mit der Leserichtungseigenschaften "von rechts nach links" an.  
  
-   **WS\_EX\_STATICEDGE** Erstellt ein Fenster mit einem dreidimensionalen Rahmenformat, in dem Elemente verwendet werden sollen, die keine Benutzereingaben akzeptieren.  
  
-   **WS\_EX\_TOOLWINDOW** Erstellt ein Toolfenster, das als unverankerte Symbolleiste verwendet werden soll.  Ein Toolfenster hat eine Titelleiste, die kürzer ist als eine normale Titelleiste, und der Fenstertitel wird mit einer kleineren Schriftart gezeichnet.  Es wird kein Toolfenster in der Taskleiste oder in dem Fenster angezeigt, das beim Drücken von ALT\+TAB angezeigt wird.  
  
-   **WS\_EX\_TOPMOST** Gibt an, dass ein in diesem Format erstelltes Fenster im Vordergrund aller vorderen Fenster angezeigt und dort bleiben soll, selbst wenn das Fenster deaktiviert wird.  Eine Anwendung kann die `SetWindowPos`\-Memberfunktion verwenden, um dieses Attribut hinzuzufügen oder zu entfernen.  
  
-   **WS\_EX\_TRANSPARENT** Gibt an, dass ein Fenster, das in diesem Format erstellt wird, transparent sein soll.  Das heißt, dass alle Fenster, die unter diesem Fenster liegen, nicht von dem Fenster verdeckt werden.  Ein Fenster, das in diesem Format erstellt wird, erhält `WM_PAINT`\-Meldungen, wenn alle darunter liegenden, nebengeordnete Fenster aktualisiert wurden.  
  
-   **WS\_EX\_WINDOWEDGE** Gibt an, dass ein Fenster einen Rahmen mit einer erhöhten Kante hat.  
  
## Siehe auch  
 [Von MFC verwendete Stile](../../mfc/reference/styles-used-by-mfc.md)   
 [CWnd::CreateEx](../Topic/CWnd::CreateEx.md)   
 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)
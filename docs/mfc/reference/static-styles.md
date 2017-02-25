---
title: "Statische Stile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SS_SUNKEN"
  - "SS_CENTER"
  - "SS_ENHMETAFILE"
  - "SS_RIGHT"
  - "SS_BLACKRECT"
  - "SS_LEFTNOWORDWRAP"
  - "SS_GRAYFRAME"
  - "SS_USERITEM"
  - "SS_GRAYRECT"
  - "SS_WHITEFRAME"
  - "SS_ETCHEDFRAME"
  - "SS_ETCHEDVERT"
  - "SS_WHITERECT"
  - "SS_PATHELLIPSIS"
  - "SS_WORDELLIPSIS"
  - "SS_NOPREFIX"
  - "SS_BITMAP"
  - "SS_SIMPLE"
  - "SS_CENTERIMAGE"
  - "SS_BLACKFRAME"
  - "SS_OWNERDRAW"
  - "SS_REALSIZEIMAGE"
  - "SS_RIGHTJUST"
  - "SS_ICON"
  - "SS_NOTIFY"
  - "SS_ETCHEDHORZ"
  - "SS_LEFT"
  - "SS_ENDELLIPSIS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SS_BITMAP-Konstante"
  - "SS_BLACKFRAME-Konstante"
  - "SS_BLACKRECT-Konstante"
  - "SS_CENTER-Konstante"
  - "SS_CENTERIMAGE-Konstante"
  - "SS_ENDELLIPSIS-Konstante"
  - "SS_ENHMETAFILE-Konstante"
  - "SS_ETCHEDFRAME-Konstante"
  - "SS_ETCHEDHORZ-Konstante"
  - "SS_ETCHEDVERT-Konstante"
  - "SS_GRAYFRAME-Konstante"
  - "SS_GRAYRECT-Konstante"
  - "SS_ICON-Konstante"
  - "SS_LEFT-Konstante"
  - "SS_LEFTNOWORDWRAP-Konstante"
  - "SS_NOPREFIX-Konstante"
  - "SS_NOTIFY-Konstante"
  - "SS_OWNERDRAW-Konstante"
  - "SS_PATHELLIPSIS-Konstante"
  - "SS_REALSIZEIMAGE-Konstante"
  - "SS_RIGHT-Konstante"
  - "SS_RIGHTJUST-Konstante"
  - "SS_SIMPLE-Konstante"
  - "SS_SUNKEN-Konstante"
  - "SS_USERITEM-Konstante"
  - "SS_WHITEFRAME-Konstante"
  - "SS_WHITERECT-Konstante"
  - "SS_WORDELLIPSIS-Konstante"
  - "Statische Stile"
ms.assetid: a1114548-fc6d-491d-8c46-21d11b8574f5
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Statische Stile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   **SS\_BITMAP** gibt eine Bitmap soll im statischen Steuerelement angezeigt werden.  Der angegebene Text ist der Name einer Bitmap \(kein Dateiname\) an anderer Stelle definiert in der Ressourcendatei.  Das Format ignoriert die nWidth und nHeight Parameter; das Steuerelement passt sich automatisch, um die Bitmap anzupassen.  
  
-   **SS\_BLACKFRAME** gibt ein Feld mit Frame an, die mit der gleichen Farbe wie Fensterrahmen gezeichnet werden.  Die Standardeinstellung ist schwarz.  
  
-   **SS\_BLACKRECT** gibt ein Rechteck, das mit der Farbe gefüllt wird, die verwendet wird, um Fensterrahmen zu zeichnen.  Die Standardeinstellung ist schwarz.  
  
-   **SS\_CENTER** legt ein einfaches Rechteck fest und zeigt den angegebenen Text an, der im Rechteck zentriert.  Der Text wird formatiert, bevor er angezeigt wird.  Wörter, die sich nach dem Ende einer Zeile erweitern würden, werden automatisch an den Anfang der nächsten zentrierten Zeile umbrochen.  
  
-   **SS\_CENTERIMAGE** gibt an, dass, wenn die Bitmap oder das Symbol kleiner als der Clientbereich des statischen Steuerelements ist, der Rest des Clientbereichs mit der Farbe des Pixels in der oberen linken Ecke der Bitmaps oder des Symbols gefüllt wird.  Wenn statische das Steuerelement eine einzelne Textzeile enthält, wird der Text vertikal im Clientbereich des Steuerelements zentriert.  
  
-   **SS\_ENDELLIPSIS** oder **SS\_PATHELLIPSIS** ersetzt Teil der angegebenen Zeichenfolge von Ellipsen ggf., damit die Ergebnispassung im angegebenen Rechteck.  
  
     Sie können **SS\_END\_ELLIPSIS**, um Zeichen am Ende der Zeichenfolge zu ersetzen oder **SS\_PATHELLIPSIS** angeben, um Zeichen in der Mitte der Zeichenfolge zu ersetzen.  Wenn die Zeichenfolge umgekehrte Schrägstriche \(\\\) enthält **SS\_PATHELLIPSIS**, behält so viel Text nach dem letzten umgekehrten Schrägstrich, wie möglich.  
  
-   **SS\_ENHMETAFILE** gibt einer erweiterten Metadatei soll im statischen Steuerelement angezeigt werden.  Der angegebene Text ist der Name einer Metadatei.  Ein statisches Steuerelement der erweiterten Metadatei eine feste Größe hat; die Metadatei skaliert, um den Clientbereich von statischem Steuerelements anzupassen.  
  
-   **SS\_ETCHEDFRAME** zeichnet der Frame des statischen Steuerelement mithilfe des **EDGE\_ETCHED** Randformats.  
  
-   **SS\_ETCHEDHORZ** zeichnet die oberen und unteren Randes des statischen Steuerelement mithilfe des **EDGE\_ETCHED** Kante formatieren.  
  
-   **SS\_ETCHEDVERT** zeichnet die linken und rechten Randes des statischen Steuerelement mithilfe des EDGE\_ETCHED\-Randformats.  
  
-   **SS\_GRAYFRAME** gibt ein Feld mit Frame an, die mit der gleichen Farbe wie der Fensterhintergrund \(Desktop\) gezeichnet werden.  Die Standardeinstellung ist grau.  
  
-   **SS\_GRAYRECT** gibt ein Rechteck, das mit der Farbe gefüllt wird, die verwendet wird, um dem Fensterhintergrund auszufüllen.  Die Standardeinstellung ist grau.  
  
-   **SS\_ICON** legt ein Symbol ab, das im Dialogfeld angezeigt wird.  Der angegebene Text ist der Name eines Symbols \(kein Dateiname\) an anderer Stelle definiert in der Ressourcendatei.  Die `nWidth` und `nHeight`\-Parameter werden ignoriert; das Symbol passt sich automatisch.  
  
-   **SS\_LEFT** legt ein einfaches Rechteck fest und zeigt den angegebenen Text an, der im Rechteck linksbündig ist.  Der Text wird formatiert, bevor er angezeigt wird.  Wörter, die sich nach dem Ende einer Zeile erweitern würden, werden automatisch an den Anfang der nächsten links ausgerichtete Zeile umbrochen.  
  
-   **SS\_LEFTNOWORDWRAP** legt ein einfaches Rechteck fest und zeigt den angegebenen Text an, der im Rechteck linksbündig ist.  Registerkarten werden erweitert, Wörter jedoch werden nicht eingeschlossen.  Text, der nach dem Ende einer Zeile wird verkürzt erweitert.  
  
-   **SS\_NOPREFIX**, es sei denn, dass dieses Format angegeben, Windows interpretiert alle kaufmännisches Und\-Zeichen \(&\) im Text des Steuerelements, um Zugriffstastenpräfixzeichen zu sein.  In diesem Fall wird das kaufmännische Und\-Zeichen entfernt und das nächste Zeichen in der Zeichenfolge wird unterstrichen.  Wenn ein statisches Steuerelement, Text besteht, in dem diese Funktion nicht erforderlich ist, wird **SS\_NOPREFIX** hinzugefügt werden.  Dieses Format statischem Steuerelements wird mit allen definierten der statischen Steuerelemente enthalten.  Sie können **SS\_NOPREFIX** mit Formaten kombinieren, indem Sie den bitweisen OR\-Operator verwenden.  Dies ist wichtig beim Dateinamen oder andere Zeichenfolgen meist, die möglicherweise eine Anforderung des kaufmännischen Und\-Zeichens enthalten, in einem statischen Steuerelement in einem Dialogfeld angezeigt werden.  
  
-   **SS\_NOTIFY** sendet das übergeordnete Fenster **STN\_CLICKED**, **STN\_DBLCLK**, **STN\_DISABLE** und **STN\_ENABLE** Benachrichtigungsmeldungen, wenn der Benutzer auf das Steuerelement klickt oder auf.  
  
-   **SS\_OWNERDRAW** gibt an, dass der Besitzer des statischen Steuerelements zum Zeichnen des Steuerelements zuständig ist.  Das Besitzerfenster empfängt eine `WM_DRAWITEM` Meldung immer muss es gezeichnet werden.  
  
-   **SS\_REALSIZEIMAGE** verhindert ein statisches Symbol\- oder Bitmapsteuerelement, also statische Steuerelemente, die das **SS\_ICON** oder **SS\_BITMAP** Stil verfügen\), die Größe geändert werden, während sie geladen oder gezeichnet wird.  Wenn das Symbol oder die Bitmap größer als der Zielbereich ist, wird das Bild entfernt.  
  
-   **SS\_RIGHT** legt ein einfaches Rechteck fest und zeigt den angegebenen Text an, der im Rechteck rechtsbündig ausgerichtet ist.  Der Text wird formatiert, bevor er angezeigt wird.  Wörter, die sich nach dem Ende einer Zeile erweitern würden, werden automatisch an den Anfang der nächsten rechtsbündigen Zeile umbrochen.  
  
-   **SS\_RIGHTJUST** gibt an, dass die untere rechte Ecke eines statischen Steuerelements mit dem Format, **SS\_BITMAP** oder **SS\_ICON** fest bleibt ist, wenn das Steuerelement angepasst wird.  Nur die oberen und des linken Rands werden angepasst, um eine neue Bitmap oder ein Symbol verwendet.  
  
-   **SS\_SIMPLE** legt ein einfaches Rechteck fest und zeigt eine einzelne Textzeile linksbündig im Rechteck.  Die Textzeile kann nicht in jeder Hinsicht gekürzt werden oder geändert werden. \(Das übergeordnete Fenster oder das Dialogfeld des Steuerelements muss `WM_CTLCOLOR` die Meldung nicht verarbeitet werden.\)  
  
-   **SS\_SUNKEN** zeichnet einen halbversunkenen Rahmen um ein statisches Steuerelement.  
  
-   **SS\_USERITEM** gibt einen benutzerdefinierten Element an.  
  
-   **SS\_WHITEFRAME** gibt ein Feld mit Frame an, die mit der gleichen Farbe wie der Fensterhintergrund gezeichnet werden.  Der Standardwert ist Weiß.  
  
-   **SS\_WHITERECT** gibt ein Rechteck, das mit der Farbe gefüllt wird, die verwendet wird, um dem Fensterhintergrund auszufüllen.  Der Standardwert ist Weiß.  
  
-   **SS\_WORDELLIPSIS** Text nicht schneidet, der angepasst ab und fügt Auslassungspunkte hinzu.  
  
## Siehe auch  
 [Von MFC verwendete Stile](../../mfc/reference/styles-used-by-mfc.md)   
 [CStatic::Create](../Topic/CStatic::Create.md)   
 [DrawEdge](http://msdn.microsoft.com/library/windows/desktop/dd162477)   
 [Static Control Styles](http://msdn.microsoft.com/library/windows/desktop/bb760773)
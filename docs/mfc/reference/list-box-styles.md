---
title: "Listenfeldstile"
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
  - "LBS_STANDARD"
  - "LBS_NODATA"
  - "LBS_OWNERDRAWVARIABLE"
  - "LBS_EXTENDEDSEL"
  - "LBS_USETABSTOPS"
  - "LBS_WANTKEYBOARDINPUT"
  - "LBS_NOTIFY"
  - "LBS_DISABLENOSCROLL"
  - "LBS_HASSTRINGS"
  - "LBS_NOREDRAW"
  - "LBS_NOSEL"
  - "LBS_NOINTEGRALHEIGHT"
  - "LBS_MULTICOLUMN"
  - "LBS_SORT"
  - "LBS_MULTIPLESEL"
  - "LBS_OWNERDRAWFIXED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LBS_DISABLENOSCROLL-Konstante"
  - "LBS_EXTENDEDSEL-Konstante"
  - "LBS_HASSTRINGS-Konstante"
  - "LBS_MULTICOLUMN-Konstante"
  - "LBS_MULTIPLESELKonstante"
  - "LBS_NODATA-Konstante"
  - "LBS_NOINTEGRALHEIGHT-Konstante"
  - "LBS_NOREDRAW-Konstante"
  - "LBS_NOSEL-Konstante"
  - "LBS_NOTIFY-Konstante"
  - "LBS_OWNERDRAWFIXED-Konstante"
  - "LBS_OWNERDRAWVARIABLE-Konstante"
  - "LBS_SORT-Konstante"
  - "LBS_STANDARD-Konstante"
  - "LBS_USETABSTOPS-Konstante"
  - "LBS_WANTKEYBOARDINPUT-Konstante"
  - "Listenfelder, Formate"
ms.assetid: 3f357b8d-9118-4f41-9e28-02ed92d1e88f
caps.latest.revision: 12
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Listenfeldstile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   **LBS\_DISABLENOSCROLL** das Listenfeld zeigt eine deaktivierte vertikale Bildlaufleiste an, wenn das Listenfeld nicht genügend Elemente enthält, um einen Bildlauf durchzuführen.  Ohne dieses Format wird die Bildlaufleiste ausgeblendet, wenn das Listenfeld nicht genügend Elemente enthält.  
  
-   **LBS\_EXTENDEDSEL** kann der Benutzer mehrere Elemente mithilfe der UMSCHALTTASTE und der Maus oder speziellentastenkombinationen auswählen.  
  
-   **LBS\_HASSTRINGS** gibt ein Ownerdrawn Listenfeld an, das die Elemente enthält, die aus Zeichenfolgen bestehen.  Das Listenfeld wartet den Speicher und die Zeiger für die Zeichenfolgen, sodass die Anwendung die `GetText`\-Memberfunktion verwenden, um den Text für ein bestimmtes Element abzurufen.  
  
-   **LBS\_MULTICOLUMN** gibt einen mehrspaltigen Listenfeld, das einen horizontalen Bildlauf durchgeführt wird.  Die Memberfunktion `SetColumnWidth` legt die Breite der Spalten fest.  
  
-   **LBS\_MULTIPLESEL** Zeichenfolgen\-Auswahl wird beendet, wenn der Benutzer auf die Zeichenfolge klickt oder doppelklicken.  Beliebige Anzahl von Zeichenfolgen kann ausgewählt werden.  
  
-   **LBS\_NODATA** gibt einen NO\-Datenlistenfeld an.  Geben Sie dieses Format an, wenn die Anzahl der Elemente im Listenfeld tausend überschreitet.  Ein NO\-Datenlistenfeld muss das **LBS\_OWNERDRAWFIXED** Stil verfügen, doch darf das **LBS\_SORT** oder **LBS\_HASSTRINGS** Format aufweisen.  
  
     Ein NO\-Datenlistenfeld ähnelt einem Ownerdrawn Listenfeld, dass keine Zeichenfolgen oder Bitmapdaten für ein Element.  Befehle, ein Element hinzuzufügen, einzufügen oder zu löschen ignorieren immer alle angegebenen Elementdaten; Anforderungen, eine Zeichenfolge innerhalb des Fail des Listenfelds immer zu suchen.  Das System sendet die Meldung im `WM_DRAWITEM` Besitzerfenster, wenn ein Element gezeichnet werden muss.  Der itemID Member `DRAWITEMSTRUCT` der Struktur, die `WM_DRAWITEM` mit der Meldung übergeben wird, gibt die Zeilennummer des zu zeichnenden Elements, an.  Ein NO\-Datenlistenfeld sendet keine Meldung `WM_DELETEITEM`.  
  
-   **LBS\_NOINTEGRALHEIGHT** die Größe des Listenfelds ist genau die Größe, die von der Anwendung bereitgestellte, als sie das Listenfeld erstellt hat.  Normalerweise skaliert Windows ein Listenfeld, dass das Listenfeld nicht partielle Elemente anzeigt.  
  
-   **LBS\_NOREDRAW** Listenfeldanzeige nicht aktualisiert, wenn Änderungen vorgenommen werden.  Dieses Format können jederzeit geändert werden, indem eine Meldung sendet. **WM\_SETREDRAW**  
  
-   **LBS\_NOSEL** gibt an, dass das Listenfeld die Elemente enthält, die angezeigt werden aber nicht ausgewählt werden können.  
  
-   **LBS\_NOTIFY** übergeordnetes Fenster empfängt eine Eingabemeldung, wenn der Benutzer auf eine Zeichenfolge klickt oder doppelklicken.  
  
-   **LBS\_OWNERDRAWFIXED** Der Besitzer des Listenfelds ist für das Zeichnen des Inhalts zuständig; die Elemente im Listenfeld sind auf dieselbe Höhe.  
  
-   **LBS\_OWNERDRAWVARIABLE** Der Besitzer des Listenfelds ist für das Zeichnen des Inhalts zuständig; die Elemente im Listenfeld sind in der Höhe variiert.  
  
-   **LBS\_SORT** Zeichenfolgen im Listenfeld sind alphabetisch sortiert.  
  
-   **LBS\_STANDARD** Zeichenfolgen im Listenfeld sind alphabetisch sortiert, und das übergeordnete Fenster empfängt eine Eingabemeldung, wenn der Benutzer auf eine Zeichenfolge klickt oder doppelklicken.  Das Listenfeld enthält Rahmen auf allen Seiten.  
  
-   **LBS\_USETABSTOPS** kann ein Listenfeld, um die Erkennung und Erweiterung von Tabstoppzeichen, wenn die zugehörigen Zeichenfolgen gezeichnet wird.  Die Standardtabstopppositionen sind 32 Dialogeinheiten. \(A\-Dialogfeldeinheit ist ein horizontaler oder vertikaler Abstand.  Eine horizontale Dialogfeldeinheit entspricht ein viertel der aktuellen Dialogfeldbasis\-Breiteneinheit.  Die Dialogfeldbasiseinheiten werden anhand der Höhe und Breite der aktuellen Systemschriftart abgeleitet.  Die **GetDialogBaseUnits** Windows\-Funktion gibt den aktuellen Dialogfeldbasiseinheiten in Pixel\) zurück. Dieses Format sollte nicht mit **LBS\_OWNERDRAWFIXED** verwendet werden.  
  
-   **LBS\_WANTKEYBOARDINPUT** Der Besitzer des Listenfelds empfängt Nachrichten `WM_VKEYTOITEM` oder `WM_CHARTOITEM`, wenn der Benutzer eine Taste drückt, während das Listenfeld Eingabefokus hat.  Dadurch kann eine Anwendung, die spezielle Verarbeitung auf der Tastatureingabe auszuführen.  
  
## Siehe auch  
 [Von MFC verwendete Stile](../../mfc/reference/styles-used-by-mfc.md)   
 [CListBox::Create](../Topic/CListBox::Create.md)   
 [List Box Styles](http://msdn.microsoft.com/library/windows/desktop/bb775149)
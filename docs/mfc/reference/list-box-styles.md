---
title: Listenfeldstile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LBS_STANDARD
- LBS_NODATA
- LBS_OWNERDRAWVARIABLE
- LBS_EXTENDEDSEL
- LBS_USETABSTOPS
- LBS_WANTKEYBOARDINPUT
- LBS_NOTIFY
- LBS_DISABLENOSCROLL
- LBS_HASSTRINGS
- LBS_NOREDRAW
- LBS_NOSEL
- LBS_NOINTEGRALHEIGHT
- LBS_MULTICOLUMN
- LBS_SORT
- LBS_MULTIPLESEL
- LBS_OWNERDRAWFIXED
dev_langs:
- C++
helpviewer_keywords:
- LBS_NOSEL constant [MFC]
- LBS_NOREDRAW constant [MFC]
- LBS_HASSTRINGS constant [MFC]
- LBS_OWNERDRAWFIXED constant [MFC]
- LBS_WANTKEYBOARDINPUT constant [MFC]
- LBS_STANDARD constant [MFC]
- LBS_MULTIPLESEL constant [MFC]
- LBS_OWNERDRAWVARIABLE constant [MFC]
- LBS_DISABLENOSCROLL constant [MFC]
- LBS_NODATA constant [MFC]
- list boxes [MFC], styles
- LBS_EXTENDEDSEL constant [MFC]
- LBS_MULTICOLUMN constant [MFC]
- LBS_NOTIFY constant [MFC]
- LBS_USETABSTOPS constant [MFC]
- LBS_NOINTEGRALHEIGHT constant [MFC]
- LBS_SORT constant
ms.assetid: 3f357b8d-9118-4f41-9e28-02ed92d1e88f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8f52734e26d1965811aded67bc1e1dde6a2c28bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="list-box-styles"></a>Listenfeldstile
-   **LBS_DISABLENOSCROLL** das Listenfeld zeigt eine deaktivierte vertikale scrollleiste Wenn das Listenfeld nicht genügend Elemente einen Bildlauf durchführen enthalten. Ohne diesen Stil wird die Scrollleiste ausgeblendet, wenn das Listenfeld nicht genügend Elemente enthält.  
  
-   **LBS_EXTENDEDSEL** der Benutzer kann mehrere Elemente, die die UMSCHALTTASTE gedrückt und Maus oder spezielle Schlüsselkombinationen auswählen.  
  
-   **LBS_HASSTRINGS** gibt ein Besitzer gezeichnetes Listenfeld, die aus Zeichenfolgen bestehen Elemente enthält. Im Listenfeld verwaltet den Arbeitsspeicher und die Zeiger für die Zeichenfolgen, damit die Anwendung verwenden, kann die `GetText` Memberfunktion um den Text für ein bestimmtes Element abzurufen.  
  
-   **LBS_MULTICOLUMN** gibt ein mehrspaltiges Listenfeld, das ein horizontaler Bildlauf durchgeführt wird. Die `SetColumnWidth` Member-Funktion legt die Breite der Spalten fest.  
  
-   **LBS_MULTIPLESEL** Zeichenfolge Auswahl umgeschaltet, jedes Mal, die der Benutzer klickt oder die Zeichenfolge doppelklickt. Eine beliebige Anzahl von Zeichenfolgen kann ausgewählt werden.  
  
-   **LBS_NODATA** gibt ein Listenfeld keine Daten an. Geben Sie dieses Format, wenn die Anzahl der Elemente im Listenfeld Tausend überschreitet. Ein Listenfeld keine Daten müssen die **LBS_OWNERDRAWFIXED** formatieren muss jedoch nicht die **LBS_SORT** oder **LBS_HASSTRINGS** Stil.  
  
     Ein Listenfeld ohne-Daten ähnelt ein vom Besitzer gezeichnetes Listenfeld aus, mit dem Unterschied, dass er keine Zeichenfolge oder eine Bitmap-Daten für ein Element enthält. Befehle zum Hinzufügen, einfügen oder Löschen eines Elements ein beliebiges Element Daten immer ignorieren Anforderungen nach einer Zeichenfolge innerhalb des Listenfelds immer ein Fehler auf. Das System sendet die `WM_DRAWITEM` Nachricht an das Besitzerfenster, wenn ein Element gezeichnet werden muss. Mitglied der Element-ID der `DRAWITEMSTRUCT` übergebenen Struktur mit den `WM_DRAWITEM` Meldung gibt die Zeilennummer des Elements, gezeichnet werden soll. Ein Listenfeld keine Daten sendet keine `WM_DELETEITEM` Nachricht.  
  
-   **LBS_NOINTEGRALHEIGHT** die Größe des Listenfelds ist genau der Größe, die von der Anwendung angegeben werden, wenn sie im Listenfeld erstellt. Windows-Größen in der Regel ein Listenfeld, damit das Listenfeld nicht Elemente abgeschnitten angezeigt werden.  
  
-   **LBS_NOREDRAW** Listenfeld Anzeige wird nicht aktualisiert werden, wenn Änderungen vorgenommen werden. Dieses Format kann jedoch jederzeit geändert werden, durch Senden einer **WM_SETREDRAW** Nachricht.  
  
-   **LBS_NOSEL** gibt an, dass das Listenfeld Elemente enthält, die angezeigt, aber nicht ausgewählt werden können.  
  
-   **LBS_NOTIFY** übergeordnete Fenster eine Eingabenachricht empfängt, wenn der Benutzer klickt oder eine Zeichenfolge doppelklickt.  
  
-   **LBS_OWNERDRAWFIXED** der Besitzer des Listenfelds ist für das Zeichnen der Inhalte verantwortlich; die Elemente im Listenfeld werden die gleiche Höhe.  
  
-   **LBS_OWNERDRAWVARIABLE** der Besitzer des Listenfelds ist für das Zeichnen der Inhalte verantwortlich; die Elemente im Listenfeld werden die Variablen in Höhe.  
  
-   **LBS_SORT** Zeichenfolgen in der Liste alphabetisch sortiert.  
  
-   **LBS_STANDARD** Zeichenfolgen in der Liste alphabetisch sortiert, und das übergeordnete Fenster eine Eingabenachricht empfängt, wenn der Benutzer klickt oder eine Zeichenfolge doppelklickt. Im Listenfeld werden die Rahmen auf allen Seiten enthält.  
  
-   **LBS_USETABSTOPS** ermöglicht ein Listenfeld zu erkennen und Erweitern von Tabulatorzeichen beim Zeichnen von Zeichenfolgen. Die Registerkarte Standardpositionen sind 32 Dialogeinheiten. (Eine Dialogeinheit ist ein horizontalen oder vertikalen Abstand. Eine horizontale Dialogeinheit ist ein Viertel des die aktuelle Basis Breite Dialogeinheit gleich. Die Basis Dialogeinheiten werden basierend auf die Höhe und Breite der aktuellen Systemschriftart berechnet. Die **GetDialogBaseUnits** Windows-Funktion gibt den aktuellen Dialogfeld Basis Einheiten in Pixel.) Dieses Format sollte nicht verwendet werden, mit **LBS_OWNERDRAWFIXED**.  
  
-   **LBS_WANTKEYBOARDINPUT** erhält der Besitzer des Listenfelds `WM_VKEYTOITEM` oder `WM_CHARTOITEM` Nachrichten, wenn der Benutzer eine Taste drückt, während Sie im Listenfeld den Eingabefokus besitzt. Dies kann eine Anwendung auf die Tastatureingaben speziellen Verarbeitungsschritte ausgeführt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Von MFC verwendete Stile](../../mfc/reference/styles-used-by-mfc.md)   
 [CListBox::Create](../../mfc/reference/clistbox-class.md#create)   
 [Liste Feld Stile](http://msdn.microsoft.com/library/windows/desktop/bb775149)


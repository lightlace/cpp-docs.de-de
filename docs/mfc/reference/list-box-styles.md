---
title: Listenfeldstile | Microsoft-Dokumentation
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
- LBS_NOSEL constant
- LBS_NOREDRAW constant
- LBS_HASSTRINGS constant
- LBS_OWNERDRAWFIXED constant
- LBS_WANTKEYBOARDINPUT constant
- LBS_STANDARD constant
- LBS_MULTIPLESEL constant
- LBS_OWNERDRAWVARIABLE constant
- LBS_DISABLENOSCROLL constant
- LBS_NODATA constant
- list boxes, styles
- LBS_EXTENDEDSEL constant
- LBS_MULTICOLUMN constant
- LBS_NOTIFY constant
- LBS_USETABSTOPS constant
- LBS_NOINTEGRALHEIGHT constant
- LBS_SORT constant
ms.assetid: 3f357b8d-9118-4f41-9e28-02ed92d1e88f
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 8e038e5cef50bd15df85c9d7f8b213b54ed03825
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="list-box-styles"></a>Listenfeldstile
-   **LBS_DISABLENOSCROLL** im Listenfeld zeigt eine deaktivierte vertikale Bildlaufleiste Wenn im Listenfeld nicht genügend Elemente einen Bildlauf durchführen enthält. Ohne diesen Stil wird die Scrollleiste ausgeblendet, wenn das Listenfeld nicht genügend Elemente enthält.  
  
-   **LBS_EXTENDEDSEL** der Benutzer kann mehrere Elemente die UMSCHALTTASTE gedrückt und Maus oder spezielle Tastenkombinationen auswählen.  
  
-   **LBS_HASSTRINGS** gibt eine Ownerdrawn-Listenfeld, das aus Zeichenfolgen bestehen Elemente enthält. Im Listenfeld werden den Speicher und die Zeiger für die Zeichenfolgen verwaltet, sodass die Anwendung verwenden, kann die `GetText` Member-Funktion, um den Text für ein bestimmtes Element abzurufen.  
  
-   **LBS_MULTICOLUMN** gibt ein mehrspaltiges Listenfeld, die ein horizontaler Bildlauf durchgeführt wird. Der `SetColumnWidth` Member-Funktion legt die Breite der Spalten fest.  
  
-   **LBS_MULTIPLESEL** Zeichenfolge Auswahl umgeschaltet, jedes Mal der Benutzer klickt oder die Zeichenfolge doppelklickt. Eine beliebige Anzahl von Zeichenfolgen kann ausgewählt werden.  
  
-   **LBS_NODATA** gibt ein Listenfeld keine Daten an. Geben Sie dieses Format, wenn die Anzahl der Elemente im Listenfeld Tausend überschreitet. Ein Listenfeld keine Daten müssen die **LBS_OWNERDRAWFIXED** formatieren muss jedoch nicht die **LBS_SORT** oder **LBS_HASSTRINGS** Stil.  
  
     Ein Listenfeld keine Daten ähnelt einem Ownerdrawn-Listenfeld er keine Zeichenfolge oder eine Bitmap-Daten für ein Element enthält. Befehle zum Hinzufügen, einfügen oder Löschen eines Elements ein beliebiges Element Daten immer ignorieren nach einer Zeichenfolge innerhalb des Listenfelds immer tritt ein Fehler auf. Das System sendet die `WM_DRAWITEM` Nachricht an das Besitzerfenster an, wenn ein Element gezeichnet werden muss. Mitglied der Element-ID der `DRAWITEMSTRUCT` übergebenen Struktur mit dem `WM_DRAWITEM` Meldung gibt die Zeilennummer des Elements, das gezeichnet werden soll. Ein Listenfeld keine Daten sendet keine `WM_DELETEITEM` Nachricht.  
  
-   **LBS_NOINTEGRALHEIGHT** die Größe des Listenfelds ist genau die Größe, die von der Anwendung angegeben werden, wenn sie im Listenfeld erstellt. Windows-Größen in der Regel ein Listenfeld, damit das Listenfeld Teilelemente nicht angezeigt wird.  
  
-   **LBS_NOREDRAW** im Listenfeld angezeigt wird nicht aktualisiert, wenn Änderungen vorgenommen werden. Dieses Format kann jederzeit geändert werden, durch das Senden einer **WM_SETREDRAW** Nachricht.  
  
-   **LBS_NOSEL** gibt an, dass im Listenfeld Elemente enthält, die angezeigt, aber nicht ausgewählt werden können.  
  
-   **LBS_NOTIFY** übergeordnete Fenster eine Eingabenachricht empfängt, wenn der Benutzer klickt oder eine Zeichenfolge doppelklickt.  
  
-   **LBS_OWNERDRAWFIXED** der Besitzer des Listenfelds ist dafür verantwortlich, ihren Inhalt zu zeichnen, die Elemente im Listenfeld werden die gleiche Höhe.  
  
-   **LBS_OWNERDRAWVARIABLE** der Besitzer des Listenfelds ist dafür verantwortlich, ihren Inhalt zu zeichnen, sind die Elemente im Listenfeld Variable Höhe.  
  
-   **LBS_SORT** Zeichenfolgen im Listenfeld werden alphabetisch sortiert.  
  
-   **LBS_STANDARD** Zeichenfolgen im Listenfeld werden alphabetisch sortiert, und das übergeordnete Fenster eine Eingabenachricht empfängt, wenn der Benutzer klickt oder eine Zeichenfolge doppelklickt. Das Listenfeld enthält Rahmenlinien auf allen Seiten.  
  
-   **LBS_USETABSTOPS** können Sie ein Listenfeld zu erkennen und Erweiterung von beim Zeichnen von Zeichenfolgen Tabstoppzeichen. Die Registerkarte Standardpositionen sind 32 Dialogeinheiten. (Eine Dialogeinheit ist eine horizontale oder vertikale Abstand. Eine horizontale Dialogeinheit entspricht ein Viertel der aktuellen Dialogfeld Basis Breite Einheit. Die Basis Dialogeinheiten werden basierend auf der Höhe und Breite des aktuellen Systemschriftart berechnet. Die **GetDialogBaseUnits** Windows-Funktion gibt das aktuelle Dialogfeld Basiseinheit in Pixel.) Dieses Format sollte nicht verwendet werden, mit **LBS_OWNERDRAWFIXED**.  
  
-   **LBS_WANTKEYBOARDINPUT** erhält der Besitzer des Listenfelds `WM_VKEYTOITEM` oder `WM_CHARTOITEM` Nachrichten, wenn der Benutzer eine Taste drückt, während das Listenfeld den Eingabefokus besitzt. Dies kann eine Anwendung auf die Tastatureingabe speziellen Verarbeitungsschritte ausgeführt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Von MFC verwendete Stile](../../mfc/reference/styles-used-by-mfc.md)   
 [CListBox::Create](../../mfc/reference/clistbox-class.md#create)   
 [Liste Feld Stile](http://msdn.microsoft.com/library/windows/desktop/bb775149)



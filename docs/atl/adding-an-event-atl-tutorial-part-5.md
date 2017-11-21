---
title: "Hinzufügen eines Ereignisses (ATL-Lernprogramm, Teil 5) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
ms.assetid: 2de12022-3148-4ce3-8606-8a9d4274f0e9
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8cef973849a9af88cd952be69ce9d33e7a516d7a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="adding-an-event-atl-tutorial-part-5"></a>Hinzufügen eines Ereignisses (ATL-Lernprogramm, Teil 5)
In diesem Schritt fügen Sie eine `ClickIn` und ein `ClickOut` Ereignis, um das ATL-Steuerelement. Sie immer dann ausgelöst, die `ClickIn` -Ereignis, wenn der Benutzer innerhalb des Polygons und Feuer klickt `ClickOut` außerhalb der Benutzer klickt. Die Aufgaben, auf ein Ereignis hinzufügen werden wie folgt:  
  
-   Hinzufügen der `ClickIn` und `ClickOut` Methoden  
  
-   Beim Generieren der Typbibliothek  
  
-   Implementieren der Verbindungspunkt-Schnittstellen  
  
## <a name="adding-the-clickin-and-clickout-methods"></a>Hinzufügen der Methoden ClickIn und ClickOut  
 Wenn Sie das ATL-Steuerelement in Schritt 2 erstellt haben, ausgewählt der **Verbindungspunkte** Kontrollkästchen. Dies erstellt die `_IPolyCtlEvents` Schnittstelle in der Datei Polygon.idl. Beachten Sie, dass der Schnittstellenname mit einem Unterstrich beginnt. Dies ist eine Konvention, um anzugeben, dass die eine interne Schnittstelle handelt. Daher können die Programme, die Ihnen ermöglichen, COM-Objekte zu durchsuchen auswählen, nicht auf die Schnittstelle für den Benutzer anzuzeigen. Beachten Sie auch diese Auswahl **Verbindungspunkte** die folgende Zeile hinzugefügt, in der Datei Polygon.idl, um anzugeben, dass `_IPolyCtlEvents` ist der Standard-Quellschnittstelle:  
  
 `[default, source] dispinterface _IPolyCtlEvents;`  
  
 Source-Attribut gibt an, dass das Steuerelement ist die Quelle der Benachrichtigungen, damit er diese Schnittstelle für den Container aufgerufen wird.  
  
 Fügen Sie jetzt die `ClickIn` und `ClickOut` Methoden, um die `_IPolyCtlEvents` Schnittstelle.  
  
#### <a name="to-add-the-clickin-and-clickout-methods"></a>So fügen Sie die Methoden ClickIn und ClickOut hinzu  
  
1.  Erweitern Sie in der Klassenansicht Polygon und PolygonLib, um _IPolyCtlEvents anzuzeigen.  
  
2.  Mit der rechten Maustaste _IPolyCtlEvents. Klicken Sie im Kontextmenü auf **hinzufügen**, und klicken Sie dann auf **Methode hinzufügen**.  
  
3.  Wählen Sie eine **Rückgabetyp** von `void`.  
  
4.  Geben Sie `ClickIn` in der **Methodennamen** Feld.  
  
5.  Klicken Sie unter **Parameterattribute**, wählen die **in** Feld.  
  
6.  Wählen Sie eine **Parametertyp** von `LONG`.  
  
7.  Typ `x` als die **Parametername**, und klicken Sie auf **hinzufügen**.  
  
8.  Wiederholen Sie die Schritte 5 bis 7, dieses Mal für eine **Parametername** von `y`.  
  
9. Klicken Sie auf **Weiter**.  
  
10. Typ `method ClickIn` als die **Helpstring**.  
  
11. Klicken Sie auf **Fertig stellen**.  
  
12. Wiederholen Sie die obengenannten Schritte, um zu definieren eine `ClickOut` Methode mit dem gleichen `LONG` Parameter `x` und `y`, die gleiche **Parameterattribute** und demselben `void` Rückgabetyp.  
  
 Überprüfen Sie die Datei Polygon.idl, um festzustellen, ob der Code hinzugefügt wurde die `_IPolyCtlEvents` Disp-Schnittstelle.  
  
 Die `_IPolyCtlEvents` Disp-Schnittstelle in der Datei Polygon.idl sollte jetzt wie folgt aussehen:  
  
 [!code-cpp[NVC_ATL_Windowing#56](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_1.idl)]  
  
 Die `ClickIn` und `ClickOut` Methoden verwenden die x- und y-Koordinaten des Punkts geklickt wurde, als Parameter.  
  
## <a name="generating-the-type-library"></a>Beim Generieren der Typbibliothek  
 Generieren Sie die Typbibliothek an diesem Punkt, weil der zeigen Datenverbindungs-Assistenten verwendet werden soll erhalten die Informationen, die es muss sich um einen Verbindungspunkt-Schnittstelle und einen Verbindungspunkt Container-Schnittstelle für das Steuerelement zu erstellen.  
  
#### <a name="to-generate-the-type-library"></a>Um die Typbibliothek zu generieren.  
  
1.  Erstellen Sie das Projekt neu.  
  
     - oder -   
  
2.  Mit der rechten Maustaste im Projektmappen-Explorer der Polygon.idl-Datei, und klicken Sie auf **Kompilieren** im Kontextmenü.  
  
 Dadurch wird die Datei Polygon.tlb erstellt die Typbibliothek also. Die Datei Polygon.tlb ist nicht im Projektmappen-Explorer sichtbar, da es eine Binärdatei ist und kann nicht angezeigt oder bearbeitet werden direkt.  
  
## <a name="implementing-the-connection-point-interfaces"></a>Implementieren der Verbindungspunkt-Schnittstellen  
 Implementieren Sie einen Verbindungspunkt-Schnittstelle und einen Verbindungspunkt Container-Schnittstelle für das Steuerelement. In COM werden Ereignisse über den Mechanismus der Verbindungspunkte implementiert. Zum Empfangen von Ereignissen von einem COM-Objekt, stellt ein Container zum Verbindungspunkt, den das COM-Objekt implementiert eine Advise-Verbindung her. Da ein COM-Objekt mehrere Verbindungspunkte aufweisen darf, implementiert das COM-Objekt auch eine Verbindungspunkt Container-Schnittstelle. Über diese Schnittstelle kann der Container bestimmen, welche Verbindungspunkte unterstützt werden.  
  
 Die Schnittstelle, die einen Verbindungspunkt implementiert heißt `IConnectionPoint`, und die Schnittstelle, die einen Verbindung Punkt Container implementiert heißt `IConnectionPointContainer`.  
  
 Helfen Sie beim Implementieren `IConnectionPoint`, verwenden Sie den Assistenten zum Implementieren von Verbindungspunkten. Dieser Assistent generiert die `IConnectionPoint` Schnittstelle durch die Typbibliothek lesen und implementiert eine Funktion für jedes Ereignis, das ausgelöst werden kann.  
  
#### <a name="to-use-the-implement-connection-point-wizard"></a>Assistent zum Implementieren von Verbindung verwenden  
  
1.  In der Klassenansicht Maustaste Implementierungsklasse des Steuerelements `CPolyCtl`.  
  
2.  Klicken Sie im Kontextmenü auf **hinzufügen**, und klicken Sie dann auf **Verbindungspunkt hinzufügen**.  
  
3.  Wählen Sie `_IPolyCtlEvents` aus der **Schnittstellen** aus, und doppelklicken Sie auf die sie zum Hinzufügen der **Implementieren von Verbindungspunkten** Spalte. Klicken Sie auf **Fertig stellen**. Eine Proxyklasse für den Verbindungspunkt generiert werden, in diesem Fall `CProxy_IPolyCtlEvents`.  
  
 Wenn Sie im Projektmappen-Explorer auf die Datei _IPolyCtlEvents_CP.h betrachten, sehen Sie, dass sie eine Klasse mit dem Namen hat `CProxy_IPolyCtlEvents` abgeleitet, die `IConnectionPointImpl`. _IPolyCtlEvents_CP.h definiert auch die beiden Methoden `Fire_ClickIn` und `Fire_ClickOut`, was die beiden-Koordinate Parameter in Anspruch nehmen. Sie können diese Methoden aufrufen, wenn ein Ereignis über das Steuerelement ausgelöst werden sollen.  
  
 Der Assistent ebenfalls hinzugefügt `CProxy_PolyEvents` und `IConnectionPointContainerImpl` auf mehrere Vererbungsliste des Steuerelements. Der Assistent ebenfalls verfügbar gemacht, `IConnectionPointContainer` für Sie von der COM-Zuordnung entsprechende Einträge hinzugefügt.  
  
 Sie sind fertig, implementieren den Code, um Ereignisse zu unterstützen. Nun fügen Sie Code zum Auslösen der Ereignisse zum geeigneten Zeitpunkt. Denken Sie daran, Sie sind im Begriff für das Auslösen einer `ClickIn` oder `ClickOut` Ereignis aus, wenn der Benutzer die linke Maustaste in das Steuerelement klickt. Um herauszufinden, wenn der Benutzer die Schaltfläche klickt, fügen Sie einen Handler für das `WM_LBUTTONDOWN` Nachricht.  
  
#### <a name="to-add-a-handler-for-the-wmlbuttondown-message"></a>So fügen Sie einen Handler für die Nachricht WM_LBUTTONDOWN hinzu  
  
1.  Klicken Sie in der Klassenansicht mit der rechten Maustaste der CPolyCtl-Klasse, und klicken Sie auf **Eigenschaften** im Kontextmenü.  
  
2.  In der **Eigenschaften** Fenster, klicken Sie auf die **Nachrichten** Symbol, und klicken Sie dann auf `WM_LBUTTONDOWN` aus der Liste auf der linken Seite.  
  
3.  Klicken Sie in der Dropdownliste auf  **\<hinzufügen > OnLButtonDown**. Die `OnLButtonDown` PolyCtl.h Handlerdeklaration hinzugefügt, und die Handlerimplementierung PolyCtl.cpp hinzugefügt.  
  
 Als Nächstes ändern Sie den Ereignishandler an.  
  
#### <a name="to-modify-the-onlbuttondown-method"></a>So ändern Sie die OnLButtonDown-Methode  
  
1.  Ändern Sie den Code der umfasst die `OnLButtonDown` Methode in PolyCtl.cpp (Code platziert, die vom Assistenten gelöscht), damit er wie folgt aussieht:  
  
     [!code-cpp[NVC_ATL_Windowing#57](../atl/codesnippet/cpp/adding-an-event-atl-tutorial-part-5_2.cpp)]  
  
 Dies ermöglicht die Verwendung der Punkte berechnet, in Code die `OnDraw` Funktion, um einen Bereich zu erstellen, das erkennt Mausklicks des Benutzers mit dem Aufruf von `PtInRegion`.  
  
 Die `uMsg` Parameter ist die ID des Windows-Meldung, die verarbeitet wird. Dadurch können Sie eine bestimmte Funktion vorhanden sein, die einen Bereich von Nachrichten verarbeitet. Die `wParam` und `lParam` Parameter sind die Standardwerte für die Nachricht verarbeitet wird. Der Parameter bHandled können Sie angeben, ob die Funktion die Nachricht oder nicht verarbeitet. Der Wert wird standardmäßig auf festgelegt `TRUE` , um anzugeben, dass die Funktion die Nachricht behandelt, aber Sie sie, um festlegen können `FALSE`. Dies bewirkt, dass ATL zum Suchen nach einer anderen Meldungshandlerfunktion zum Senden der Nachricht zu fortfahren.  
  
## <a name="building-and-testing-the-control"></a>Erstellen und Testen des Steuerelements  
 Jetzt können Sie Ihre Ereignisse. Erstellen Sie das Steuerelement, und starten Sie den Testcontainer für ActiveX-Steuerelemente erneut. Zeigen Sie diesmal, das Ereignisprotokoll-Fenster. Um Ereignisse an das Fenster "Ausgabe" weiterzuleiten, klicken Sie auf **Protokollierung** aus der **Optionen** Menü **Protokoll, um das Fenster "Ausgabe"**. Fügen Sie das Steuerelement, und klicken Sie im Fenster auf. Beachten Sie, dass `ClickIn` wird ausgelöst, wenn Sie innerhalb des ausgefüllten Polygons klicken und `ClickOut` wird ausgelöst, wenn Sie außerhalb davon klicken.  
  
 Als Nächstes fügen Sie eine Eigenschaftenseite.  
  
 [Zurück zu Schritt 4](../atl/changing-the-drawing-code-atl-tutorial-part-4.md) &#124; [Mit Schritt 6 fort](../atl/adding-a-property-page-atl-tutorial-part-6.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Lernprogramm](../atl/active-template-library-atl-tutorial.md)


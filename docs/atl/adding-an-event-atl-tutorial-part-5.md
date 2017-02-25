---
title: "Hinzuf&#252;gen eines Ereignisses (ATL-Lernprogramm, Teil 5) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
ms.assetid: 2de12022-3148-4ce3-8606-8a9d4274f0e9
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Hinzuf&#252;gen eines Ereignisses (ATL-Lernprogramm, Teil 5)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Schritt fügen Sie `ClickIn` und ein Ereignis hinzu `ClickOut` ATL\-Steuerelement hinzu.  Sie lösen das `ClickIn`\-Ereignis aus, wenn der Benutzer in das Polygon und des Datei `ClickOut` klickt, wenn der Benutzer außerhalb klickt.  Die Aufgaben, ein Ereignis hinzuzufügen, sind wie folgt:  
  
-   Hinzufügen der `ClickIn` und `ClickOut`\-Methoden  
  
-   Generieren der Typbibliothek  
  
-   Implementieren der Verbindungspunkt\-Schnittstellen  
  
## Hinzufügen der Methoden ClickIn und ClickOut  
 Als Sie das ATL\-Steuerelement in Schritt 2 erstellt haben, haben Sie das Kontrollkästchen **Verbindungspunkte**.  Dies hat die `_IPolyCtlEvents`\-Schnittstelle in der Polygon.idl\-Datei.  Beachten Sie die Schnittstellennameanfänge mit einem Unterstrich.  Dies ist eine Konvention, anzugeben, dass die Schnittstelle eine interne Schnittstelle ist.  Daher können Programme, die es Ihnen ermöglichen, COM\-Objekte zu durchsuchen, auswählen, um die Schnittstelle nicht für den Benutzer anzuzeigen.  Beachten Sie auch das, das **Verbindungspunkte** auswählt, hat die folgende Zeile in der Polygon.idl\-Datei, um anzugeben, dass `_IPolyCtlEvents` die standardmäßige Quellschnittstelle ist:  
  
 `[default, source] dispinterface _IPolyCtlEvents;`  
  
 Das Quellattribut gibt an, dass das Steuerelement die Quelle der Benachrichtigungen ist, daher wird diese Schnittstelle im Container auf.  
  
 Fügen Sie nun `ClickIn` hinzu und `ClickOut`\-Methoden zu `_IPolyCtlEvents` schließen an.  
  
#### Um die Methoden ClickIn und ClickOut hinzufügen  
  
1.  Erweitern Sie in der Klassenansicht Polygon und PolygonLib, um \_IPolyCtlEvents anzuzeigen.  
  
2.  Klicken Sie auf \_IPolyCtlEvents mit der rechten Maustaste.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Methode hinzufügen**.  
  
3.  Wählen Sie **Rückgabetyp** von `void` aus.  
  
4.  Gibt `ClickIn`**Methodenname** im Feld.  
  
5.  Die **Parameterattributein** wählen Sie das Feld aus.  
  
6.  Wählen Sie **Parametertyp** von `LONG` aus.  
  
7.  Geben Sie `x` als **Parametername** ein, und klicken Sie auf **Hinzufügen**.  
  
8.  Wiederholen Sie die Schritte 5 bis 7, dieses Mal für **Parametername** von y.  
  
9. Klicken Sie auf **Weiter**.  
  
10. Typ `- Methode ClickIn` als **helpstring**.  
  
11. Klicken Sie auf **Fertig stellen**.  
  
12. Wiederholen Sie die Schritte oben, um eine `ClickOut`\-Methode mit denselben Parametern `LONG``x` und `y`, dieselbe **Parameterattribute** zu definieren und der gleiche `void` Rückgabetyp.  
  
 Überprüfen Sie die Polygon.idl\-Datei, um anzuzeigen, dass der Code zur `_IPolyCtlEvents` Dispatchschnittstelle hinzugefügt wurde.  
  
 Die `_IPolyCtlEvents` Dispatchschnittstelle in der Polygon.idl\-Datei sollte nun wie folgt aussehen:  
  
 [!CODE [NVC_ATL_Windowing#56](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#56)]  
  
 Die `ClickIn` und `ClickOut`\-Methoden nehmen die x\- und y\-Koordinaten für per Punkts als Parameter.  
  
## Generieren der Typbibliothek  
 Generieren Sie die Typbibliothek an diesem Punkt, da der Verbindungspunkt\-Assistent sie verwendet, um auf die Informationen abrufen, die sie eine Verbindungspunkt\-Schnittstelle und eine Verbindungspunktcontainerschnittstelle für das Steuerelement erstellen.  
  
#### Um die Typbibliothek generieren  
  
1.  Erstellen Sie das Projekt neu.  
  
     \- oder \-  
  
2.  Klicken Sie auf den Polygon.idl\-Datei in Projektmappen\-Explorer mit der rechten Maustaste auf und klicken Sie auf **Kompilieren** im Kontextmenü.  
  
 Damit wird die Polygon.tlb\-Datei, die die Typbibliothek ist.  Die Polygon.tlb\-Datei ist nicht im Projektmappen\-Explorer angezeigt, da es eine Binärdatei ist und nicht direkt angezeigt oder bearbeitet werden kann.  
  
## Implementieren der Verbindungspunkt\-Schnittstellen  
 Implementieren Sie eine Verbindungspunkt\-Schnittstelle und eine Verbindungspunktcontainerschnittstelle für das Steuerelement.  In COM werden Ereignisse durch den Mechanismus von Verbindungspunkten implementiert.  Um Ereignisse von einem COM\-Objekt zu empfangen, richtet ein Container eine Advise\-Verbindung dem Verbindungspunkt ein den das COM\-Objekt implementiert.  Da ein COM\-Objekt mehrere Verbindungspunkte haben kann, implementiert das COM\-Objekt auch eine Verbindungspunktcontainerschnittstelle.  Durch diese Schnittstelle kann der Container bestimmen, welche Verbindungspunkte unterstützt werden.  
  
 Die Schnittstelle, die einen Verbindungspunkt implementiert, wird `IConnectionPoint` und die Schnittstelle, die einen Verbindungspunktcontainer implementiert, wird aufgerufen `IConnectionPointContainer` aufgerufen.  
  
 Um die `IConnectionPoint` zu implementieren, verwenden Sie den Assistenten zum Implementieren von Verbindungspunkten.  Dieser Assistent generiert die `IConnectionPoint`\-Schnittstelle, indem er die Typbibliothek liest und eine Funktion für jedes Ereignis implementiert, das ausgelöst werden kann.  
  
#### Um den Assistenten zum Implementieren von Verbindungspunkten verwenden  
  
1.  Klicken Sie in der Klassenansicht auf die Implementierungsklasse `CPolyCtl` des Steuerelements mit der rechten Maustaste.  
  
2.  Klicken Sie im Kontextmenü **Hinzufügen** klicken Sie auf und dann auf **Verbindungspunkt hinzufügen**.  
  
3.  Ausgewähltes `_IPolyCtlEvents` aus der Liste **Quellschnittstellen** und doppelklicken darauf, um sie der Spalte **Verbindungspunkte implementieren** hinzuzufügen.  Klicken Sie auf **Fertig stellen**.  Eine Proxyklasse für den Verbindungspunkt wird in diesem Fall `CProxy_IPolyCtlEvents` generiert.  
  
 Wenn Sie den generierten \_IPolyCtlEvents\_CP.h\-Datei im Projektmappen\-Explorer anschauen, sehen Sie, dass sie eine Klasse hat, die `CProxy_IPolyCtlEvents` aufgerufen wird, die von `IConnectionPointImpl` abgeleitet.  \_IPolyCtlEvents\_CP.h definiert auch die zwei Methoden `Fire_ClickIn` und `Fire_ClickOut`, die die zwei koordinieren Parameter annehmen.  Sie rufen diese Methoden auf, wenn Sie ein Ereignis von dem Steuerelement auslösen möchten.  
  
 Der Assistent auch hinzugefügtes `CProxy_PolyEvents` und `IConnectionPointContainerImpl` zur Mehrfachvererbungsliste des Steuerelements.  Der Assistent auch verfügbar gemacht `IConnectionPointContainer` für Sie durch Hinzufügen von entsprechenden Einträgen zur COM\-Zuordnung.  
  
 Sie werden den Code implementiert, um Ereignisse zu unterstützen beendet.  Als Nächstes fügen Sie Code hinzu, um die Ereignisse am entsprechenden Zeitpunkt auszulösen.  Beachten Sie, `ClickIn` werden ein oder `ClickOut`\-Ereignis auslösen, wenn der Benutzer auf die linke Maustaste im Steuerelement klickt.  Um herauszufinden wenn der Benutzer auf die Schaltfläche klickt, fügen Sie einen Handler für die `WM_LBUTTONDOWN` Meldung hinzu.  
  
#### So fügen Sie einen Handler für die WM\_LBUTTONDOWN\-Meldung hinzufügen  
  
1.  Klicken Sie in der Klassenansicht auf die CPolyCtl\-Klasse mit der rechten Maustaste auf und klicken Sie auf **Eigenschaften** im Kontextmenü.  
  
2.  Im Fenster **Eigenschaften** klicken Sie auf das Symbol **Meldungen** und dann auf `WM_LBUTTONDOWN` aus der Liste links.  
  
3.  Klicken Sie in der Dropdownliste, die angezeigt wird, auf **\<Hinzufügen\> OnLButtonDown**.  Die `OnLButtonDown`\-Handlerdeklaration wird zu PolyCtl.h hinzugefügt, und die Handlerimplementierung wird zu PolyCtl.cpp hinzugefügt.  
  
 Als Nächstes ändern Sie den Handler.  
  
#### Um die OnLButtonDown\-Methode ändern  
  
1.  Ändern Sie den Code, der die `OnLButtonDown`\-Methode in PolyCtl.cpp enthält \(Code Löschen platziert vom Assistenten\) für sie wie folgt aussieht:  
  
     [!CODE [NVC_ATL_Windowing#57](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#57)]  
  
 Dieser Code verwendet die Punkte aus, die in der `OnDraw`\-Funktion berechnet werden, um einen Bereich zu erstellen, der die Mausklicks des Benutzers mit dem Aufruf von `PtInRegion` erkennt.  
  
 Der `uMsg`\-Parameter ist die ID der Windows\-Meldung, die behandelt wird.  Dies ermöglicht Ihnen, eine Funktion zu verwenden, die einen Bereich von Meldungen behandelt.  `wParam` und die `lParam`\-Parameter sind die Standardwerte für die Meldung, die behandelt wird.  Der bHandled Parameter ermöglicht es Ihnen, um anzugeben, ob die Funktion die Meldung oder unveränderte.  Standardmäßig ist der Wert auf `TRUE` festgelegt, um anzugeben, dass die Funktion die bearbeitete Meldung, aber Sie sie zu `FALSE` festlegen können.  Dadurch wird ATL, das Suchen nach einer anderen Meldungshandlerfunktion fortsetzen, um die Meldung an zu senden.  
  
## Erstellen und Testen des Steuerelements  
 Testen Sie nun die Ereignisse aus.  Erstellen Sie das Steuerelement und stellen Sie den Testcontainer für ActiveX\-Steuerelemente erneut an.  Dieses Mal, zeigen das Ereignisprotokollfenster an.  Um Ereignisse in das Ausgabefenster weiterzuleiten, klicken Sie auf **Protokollierung** vom Menü **Optionen** und wählen Sie **In Ausgabefenster protokollieren** aus.  Fügen Sie das Steuerelement und versuchen ein, die im Fenster klicken.  Beachten Sie, dass `ClickIn` ausgelöst wird, wenn Sie innerhalb des ausgefüllten Polygon klicken, und `ClickOut` wird ausgelöst, wenn Sie außerhalb davon klicken.  
  
 Als Nächstes fügen Sie eine Eigenschaftenseite hinzu.  
  
 [Zurück zu Schritt 4](../atl/changing-the-drawing-code-atl-tutorial-part-4.md) &#124; [Klicken Sie zu Schritt 6](../atl/adding-a-property-page-atl-tutorial-part-6.md)  
  
## Siehe auch  
 [Lernprogramm](../atl/active-template-library-atl-tutorial.md)
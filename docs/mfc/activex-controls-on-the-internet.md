---
title: "ActiveX-Steuerelemente f&#252;r das Internet"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Steuerelemente [C++], Erstellen"
  - "ActiveX-Steuerelemente [C++], Internet"
  - "Herunterladen von Daten mit ActiveX-Steuerelementen"
  - "Internetanwendungen [C++], ActiveX-Steuerelemente"
  - "Netzwerke [C++], Herunterladen mit ActiveX-Steuerelementen"
  - "OLE-Steuerelemente [C++], Upgrade auf ActiveX"
ms.assetid: 7ab943c8-2022-41df-9065-d629b616eeec
caps.latest.revision: 14
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# ActiveX-Steuerelemente f&#252;r das Internet
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ActiveX\-Steuerelemente sind die aktualisierte Version der OLE\-Steuerelement\-Spezifikation.  Steuerelemente sind eine primäre Architektur für das Entwickeln von programmierbaren Softwarekomponenten, die bei einer Vielzahl verschiedener Containern verwendet werden können, einschließlich COM\-bewusste Webbrowser im Internet.  Jedes ActiveX\-Steuerelement kann ein Internet\-Steuerelement sein und kann seiner Funktionalität einem aktiven Dokument hinzu oder Teil einer Webseite sein.  Steuerelemente auf einer Webseite können miteinander mithilfe der Skripterstellung kommunizieren.  
  
 ActiveX\-Steuerelemente werden nicht zum Internet beschränkt.  Ein ActiveX\-Steuerelement kann in einem Container auch verwendet werden, solange das Steuerelement diese Schnittstellen unterstützt, die von diesen Container benötigt werden.  
  
 **ActiveX\-Steuerelemente haben mehrere Vorteile und umfassen:**  
  
-   Weniger erforderliche Schnittstellen als vorherige OLE\-Steuerelemente.  
  
-   Die Möglichkeit, fensterlos und immer direkt zu aktivierenden.  
  
 **So fügen Sie ein ActiveX\-Steuerelement ist, muss ein Steuerelement:**  
  
-   Unterstützen Sie die Schnittstelle **IUnknown**.  
  
-   Stellen Sie ein COM\-Objekt.  
  
-   Export **DLLRegisterServer**  und **DLLUnRegisterServer**.  
  
-   Stützzusätzliche Schnittstellen nach Bedarf für Funktionen.  
  
## Vorhandene Steuerelemente Internet\-benutzerfreundlich erstellen  
 Das Entwerfen eines Steuerelements, das gut in einer Internet\-Umgebung funktioniert, erfordert Überlegung für die relativ niedrigen Übertragungsraten im Internet.  Sie können vorhandene Steuerelemente verwenden; hingegen gibt es Schritte, die Sie ausführen sollten, um die Codegröße auszuführen und die Steuerelementeigenschaften asynchron herunterladen zu lassen.  
  
 Um die Leistung der Steuerelemente zu verbessern, führen Sie folgende Tipps für Effizienzüberlegungen:  
  
-   Implementieren Sie die Verfahren, die im Artikel [ActiveX\-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md) beschrieben werden.  
  
-   Überlegen Sie, wie ein Steuerelement instanziiert wird.  
  
-   Achten asynchron; halten Sie nicht andere Programme.  
  
-   Laden Sie Daten in kleinen Blöcken herunter.  
  
     Wenn große Streams wie Bitmaps oder Videosignale herunterladen, greifen Sie auf die Daten eines Steuerelements asynchron in Zusammenarbeit mit dem Container zu.  Rufen Sie die Daten in einer fortlaufenden oder progressiven Weise ab und mit anderen Steuerelementen gemeinsam verwenden, die möglicherweise auch Daten abrufen.  Code kann auch asynchron herunterladen.  
  
-   Downloadcode und \- eigenschaften im Hintergrund.  
  
-   Gewordene Benutzeroberfläche aktiv schnellstmöglich.  
  
-   Überlegen Sie, wie Daten, dauerhafte Eigenschaften und umfangreiche Daten Blobs gespeichert werden \(z ein Bitmapbild oder Videosignale\).  
  
     Steuerelemente mit beträchtlichen Mengen von dauerhafter Daten, wie große Bitmaps oder AVI\-Dateien, erfordern eine sorgfältige Aufmerksamkeit zum Herunterladen von Methode.  Ein Dokument oder eine Seite sichtbar können so schnell wie möglich werden und ermöglichen den Benutzern, die mit der Seite interagieren, während Steuerelemente Daten im Hintergrund abrufen.  
  
-   Schreiben Sie Routinen, um effiziente Codegröße und \-Laufzeit unten zu halten.  
  
     Kleine Schaltfläche und Label\-Steuerelement, mit nur einigen Bytes dauerhafter Daten, sind für Internet\-Umgebung geeignet und funktionieren innere Browser des gut.  
  
-   Betrachten Sie Status wird übermittelt bin.  
  
     Melden Sie den Container des Status im asynchronen Herunterladen und enthalten, wenn der Benutzer starten kann, um mit einer Seite interagieren und wann der Download abgeschlossen ist.  Der Container kann Status \(z % abgeschlossen\) für Benutzer anzuzeigen.  
  
-   Überlegen Sie, wie Steuerelemente auf dem Clientcomputer registriert werden.  
  
## Erstellen eines neuen ActiveX\-Steuerelements  
 Wenn Sie ein neues Steuerelement mithilfe des Anwendungs\-Assistenten erstellen, können Sie auswählen, um Unterstützung für asynchrone Moniker sowie andere Optimierungen zu aktivieren.  Um Unterstützung Downloadsteuerelementeigenschaften asynchron hinzuzufügen, führen Sie folgende Schritte aus:  
  
#### Um das Projekt mit dem MFC\-ActiveX\-Steuerelement\-Assistenten erstellen  
  
1.  auf `New` im Menü **Datei**.  
  
2.  Ausgewähltes **MFC\-ActiveX\-Steuerelement\-Assistent** von Visual C\+\+\-Projekten und nennen das Projekt.  
  
3.  Klicken Sie auf der Seite **Steuerelementeinstellungen** die Option **Lädt Eigenschaften asynchron** aus.  Diese Option auswählen, installieren das threadbereite Zustandseigenschaften und das Changed\-Ereignis Bereit des Zustands für Sie.  
  
     Sie können andere Optimierungen, wie **Fensterlose Aktivierung** auch auswählen, das in [ActiveX\-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md) beschrieben wird.  
  
4.  Wählen Sie **Fertig stellen**, um das Projekt zu erstellen.  
  
#### So erstellen Sie eine Klasse abgeleitet von CDataPathProperty  
  
1.  Erstellen Sie eine Klasse, die von `CDataPathProperty` abgeleitet wird.  
  
2.  In jeder der Quelldateien, die die Headerdatei für das Steuerelement enthält, fügen Sie der Headerdatei für diese Klasse vor hinzu.  
  
3.  Überschreiben Sie in dieser Klasse `OnDataAvailable`.  Diese Funktion wird aufgerufen, wenn Daten zur Anzeige verfügbar sind.  Während Daten verfügbar sind, können Sie es behandeln jede Methode, die Sie auswählen, indem Sie beispielsweise progressiv diese rendern.  
  
     Der folgende Codeauszug ist ein einfaches Beispiel für Daten in einem Bearbeitungssteuerelement progressiv anzeigen.  Beachten Sie die Verwendung des Flags **BSCF\_FIRSTDATANOTIFICATION**, das Bearbeitungssteuerelement zu löschen.  
  
     [!CODE [NVC_MFCActiveXControl#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCActiveXControl#1)]  
  
     Beachten Sie, dass Sie AFXCMN.H einschließen müssen, um die `CListCtrl`\-Klasse zu verwenden.  
  
4.  Wenn Gesamtzustandsänderungen des Steuerelements \(beispielsweise, dem Laden nach initialisiert oder interaktiv\), `COleControl::InternalSetReadyState` aufrufen.  Wenn das Steuerelement nur eine Datenpfadeigenschaft verfügt, können Sie Code hinzufügen auf **BSCF\_LASTDATANOTIFICATION**, um den Container zu benachrichtigen, dass der Download abgeschlossen ist.  Beispiel:  
  
     [!CODE [NVC_MFCActiveXControl#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCActiveXControl#2)]  
  
5.  Überschreiben Sie `OnProgress`.  In `OnProgress` werden Ihnen eine Zahl die maximale Gültigkeitsbereichs und eine Zahlenvertretung wird übergeben, inwieweit am aktuellen Download ist.  Sie können diese Zahlen verwenden, um Status wie bereits verarbeitete Prozentsatz für den Benutzer anzuzeigen.  
  
 Im folgenden Verfahren wird eine Eigenschaft das Steuerelement hinzu, um die gerade berechnete Klasse zu verwenden.  
  
#### So legen Sie eine Eigenschaft hinzu  
  
1.  Klicken Sie im **Klassenansicht** auf die Schnittstelle zwischen den Bibliotheksknoten mit der rechten Maustaste und wählen **Hinzufügen**, anschließend **Eigenschaft hinzufügen** aus.  Dies startet **Assistent zum Hinzufügen von Eigenschaften**.  
  
2.  In **Assistent zum Hinzufügen von Eigenschaften** wählen Sie das Optionsfeld **Set\/Get\-Methoden** aus, geben Sie **Eigenschaftenname** beispielsweise EditControlText ein, und wählen Sie als BSTR **Eigenschaftentyp** aus.  
  
3.  Klicken Sie auf **Fertig stellen**.  
  
4.  Deklarieren Sie eine Membervariable der von `CDataPathProperty` abgeleiteten Klasse in die ActiveX\-Steuerelementklasse.  
  
     [!CODE [NVC_MFCActiveXControl#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCActiveXControl#3)]  
  
5.  Implementieren Sie die Methoden **Get\/Set**.  Für **Abrufen** geben Sie die Zeichenfolge zurück.  Für `Set` laden Sie die Eigenschaft und rufen `SetModifiedFlag` auf.  
  
     [!CODE [NVC_MFCActiveXControl#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCActiveXControl#4)]  
  
6.  In [DoPropExchange](../Topic/COleControl::DoPropExchange.md) fügen Sie die folgende Zeile hinzu:  
  
     [!CODE [NVC_MFCActiveXControl#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCActiveXControl#5)]  
  
7.  Überschreibung [ResetData](../Topic/CDataPathProperty::ResetData.md), um die Eigenschaft zu benachrichtigen, um sein Steuerelement durch Hinzufügen dieser Zeile zurückzusetzen:  
  
     [!CODE [NVC_MFCActiveXControl#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCActiveXControl#6)]  
  
## Entscheiden, ob von CDataPathProperty oder von CCachedDataPathProperty abgeleitet  
 Das vorherige Beispiel beschreibt die Schritte für das Berechnen der Eigenschaft des Steuerelements von `CDataPathProperty`.  Dies ist sinnvoll, wenn Sie Echtzeitdaten herunterladen, die sich häufig ändert, und für den Sie nicht erforderlich ist, um alle Daten übergeben, aber nur der aktuelle Wert.  Ein Beispiel ist ein Börsenticker\-Steuerelement.  
  
 Sie können auch von `CCachedDataPathProperty` abgeleitet werden.  In diesem Fall werden die heruntergeladenen Daten in einer Arbeitsspeicherdatei zwischengespeichert.  Dies ist sinnvoll, wenn Sie alle heruntergeladenen Daten übergeben müssen \- beispielsweise, ein Steuerelement, das progressiv eine Bitmap rendert.  In diesem Fall verfügt die Klasse eine Membervariable, die die Daten enthält:  
  
 `CMemFile m_Cache;`  
  
 In die ActiveX\-Steuerelementklasse können Sie diese Speicherabbilddatei in `OnDraw` verwenden, um die Daten anzuzeigen.  In dem ActiveX\-Steuerelement `CCachedDataPathProperty` abgeleitete Klasse, überschreiben Sie die Memberfunktion `OnDataAvailable` und machen Sie das Steuerelement ungültig, nachdem Sie die Basisklassenimplementierung aufgerufen haben.  
  
 [!CODE [NVC_MFCActiveXControl#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCActiveXControl#7)]  
  
## Downloading\-Daten asynchron mithilfe von ActiveX\-Steuerelementen  
 Downloadingdaten über ein Netzwerk sollten asynchron erfolgen.  Der Vorteil dazu ist, dass eine große Datenmenge übertragen werden, oder die Verbindung langsam, der Herunterladen blockiert keine anderen Prozessen auf dem Client.  
  
 Asynchrone Moniker ermöglichen es, Daten über ein Netzwerk asynchron herunterladen.  Ein Lesevorgang in einem asynchronen Moniker wird sofort zurückgegeben, wenn der Vorgang nicht abgeschlossen wurde.  
  
 Wenn nur 10 Byte verfügbaren und Lesen asynchron in einer Datei 1K aufgerufen wird, blockiert Lesen, jedoch wird nicht mit den zur Zeit verfügbaren 10 Bytes zurück.  
  
 Sie implementieren [Moniker asynchrone](../mfc/asynchronous-monikers-on-the-internet.md) mithilfe der Klasse `CAsyncMonikerFile`.  ActiveX\-Steuerelemente können jedoch die `CDataPathProperty`\-Klasse verwenden, die von `CAsyncMonikerFile` abgeleitet wird, um zu helfen, asynchrone Steuerelementeigenschaften zu implementieren.  
  
 Das ASYNDOWN\-Beispiel veranschaulicht, wie eine asynchrone Schleife mithilfe der Zeitgeber installiert, um die Daten zu lesen.  ASYNDOWN wird ausführlich im Knowledge Base\-Artikel "HOWTO beschrieben: AsyncDown veranschaulicht asynchronen Daten\-Download" \(Q177244\) und ist vom Microsoft Download Center heruntergeladen. \(Weitere Informationen über das Herunterladen Datei im Microsoft Download Center, finden Sie im Artikel "erhält wie Microsoft Support\-Dateien von den Onlinediensten" \(Q119591\) in der Microsoft Knowledge Base.\) Knowledge Base\-Artikel finden Sie auf der MSDN Library\-CD\-ROM oder unter [http:\/\/support.microsoft.com\/support](http://support.microsoft.com/support).  
  
 Die grundlegende Technik, die in ASYNDOWN verwendet wird, ist, einen Zeitgeber in **CDataPathProperty::OnDataAvailable** festlegen, um anzugeben, wann Daten verfügbar sind.  Wenn die Zeitgebermeldung empfangen wird, wird die Anwendung in 128 Byteblöcke Daten und füllt ein Bearbeitungssteuerelement aus.  Wenn Daten nicht verfügbar sind, wenn die Zeitgebermeldung bearbeitet wird, wird der Zeitgeber deaktiviert.  `OnDataAvailable` aktiviert den Zeitgeber ein, wenn mehr Daten später erhält.  
  
## Anzeigen eines Steuerelements in einer Webseite  
 Im Folgenden ein Beispiel eines Objekttags und Attribute zum Einfügen eines Steuerelements in einer Webseite.  
  
 `<OBJECT`  
  
 `CLASSID="clsid:FC25B780-75BE-11CF-8B01-444553540000"`  
  
 `CODEBASE="/ie/download/activex/iechart.ocx"`  
  
 `ID=chart1`  
  
 `WIDTH=400`  
  
 `HEIGHT=200`  
  
 `ALIGN=center`  
  
 `HSPACE=0`  
  
 `VSPACE=0`  
  
 `>`  
  
 `<PARAM NAME="BackColor" value="#ffffff">`  
  
 `<PARAM NAME="ForeColor" value="#0000ff">`  
  
 `<PARAM NAME="url" VALUE="/ie/controls/chart/mychart.txt">`  
  
 `</OBJECT>`  
  
## Aktualisieren eines vorhandenen OLE\-Steuerelements, um neue ActiveX\-Steuerelement\-Funktionen zu verwenden  
 Wenn das OLE\-Steuerelement mit einer Version von Visual C\+\+ vor 4,2 erstellt wurde, gibt es Schritte, die Sie ausführen können, um ihre Leistung zu verbessern und seine Funktionalität zu verbessern.  Ausführliche Informationen über diese Änderungen, finden Sie unter [ActiveX\-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md).  
  
 Wenn Sie asynchrone Eigenschaftenunterstützung zu einem vorhandenen Steuerelement hinzufügen, muss das threadbereite Zustandseigenschaften und `ReadyStateChange` das Ereignis selbst hinzufügen.  Im Konstruktor für das Steuerelement, fügen Sie hinzu:  
  
 [!CODE [NVC_MFCActiveXControl#8](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCActiveXControl#8)]  
  
 Sie aktualisieren den Zustand Bereit, wie der Code heruntergeladen wird, indem Sie [COleControl::InternalSetReadyState](../Topic/COleControl::InternalSetReadyState.md) aufrufen.  Ein Abstand, den Sie `InternalSetReadyState` aufrufen können, ist von der `OnProgress` \- Überschreibung von `CDataPathProperty` abgeleiteten Klasse.  
  
 Anschließend führen Sie die Schritte in [Erstellen eines neuen ActiveX\-Steuerelements](#_core_how_do_i_create_a_new_activex_control.3f).  
  
## Siehe auch  
 [MFC\-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)   
 [Grundlagen der MFC\-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)
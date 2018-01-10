---
title: "ActiveX-Steuerelemente für das Internet | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ActiveX controls [MFC], creating
- ActiveX controls [MFC], Internet
- downloading data with ActiveX controls
- OLE controls [MFC], upgrading to ActiveX
- Internet applications [MFC], ActiveX controls
- networks [MFC], downloading with ActiveX controls
ms.assetid: 7ab943c8-2022-41df-9065-d629b616eeec
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8c02d807f6b77ca7aa35ffe91b929122a3743be6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="activex-controls-on-the-internet"></a>ActiveX-Steuerelemente für das Internet
ActiveX-Steuerelemente sind die aktualisierte Version der OLE-Steuerelement-Spezifikation. Steuerelemente sind eine primäre Architektur für die Entwicklung von programmierbaren Softwarekomponenten, die in einer Vielzahl von unterschiedlichen Containern, einschließlich COM+-fähigen Webbrowser auf das Internet verwendet werden können. Jedes ActiveX-Steuerelement kann ein Internet-Steuerelement sein und können die Funktionalität eines aktiven Dokuments hinzufügen oder Teil einer Webseite. Steuerelemente auf einer Webseite können mithilfe von Skripts miteinander kommunizieren.  
  
 ActiveX-Steuerelemente sind nicht mit dem Internet beschränkt. Ein ActiveX-Steuerelement kann auch in jedem Container verwendet werden, solange das Steuerelement dieses Containers erforderlichen Schnittstellen unterstützt.  
  
 **ActiveX-Steuerelemente haben folgende Vorteile:**  
  
-   Weniger erforderlichen Schnittstellen als vorherige OLE-Steuerelemente.  
  
-   Die Fähigkeit, fensterlose sein und immer direkt aktiv.  
  
 **Damit ein ActiveX-Steuerelement werden zu können, müssen ein Steuerelement:**  
  
-   Unterstützung der **IUnknown** Schnittstelle.  
  
-   Werden Sie ein COM-Objekt.  
  
-   Exportieren Sie **DLLRegisterServer** und **DLLUnRegisterServer**.  
  
-   Unterstützen Sie zusätzliche Schnittstellen, für die Funktionalität nach Bedarf.  
  
## <a name="making-your-existing-controls-internet-friendly"></a>Wie werden vorhandene Steuerelemente Internet-freundliche  
 Entwerfen ein Steuerelement, das auch in einer Internet-Umgebung funktioniert, muss berücksichtigt werden, die relativ niedrigen Übertragungsraten im Internet. Sie können vorhandene Steuerelemente verwenden. Es gibt jedoch auch Schritte, die Sie ausführen sollten, um Verkleinern der Größe Ihres Codes und die Steuerelementeigenschaften asynchron herunterladen zu machen.  
  
 Befolgen Sie diese Tipps Leistungsaspekten Effizienz, zum Verbessern der Leistung von Steuerelementen:  
  
-   Implementieren Sie im Artikel beschriebenen Techniken [ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md).  
  
-   Erwägen Sie, wie ein Steuerelement instanziiert wird.  
  
-   Asynchron sein; Halten Sie nicht von anderen Programmen.  
  
-   Herunterladen von Daten in kleinen Blöcken.  
  
     Beim Herunterladen von umfangreiche Streams z. B. Bitmaps oder Videodaten Zugriff auf ein Steuerelement Daten asynchron in Zusammenarbeit mit dem Container. Abrufen von Daten in einer Weise inkrementell oder gleichzeitig progressiven, arbeiten gemeinsam mit anderen Steuerelementen, die auch die Daten abgerufen werden können. Code kann auch asynchron heruntergeladen werden.  
  
-   Herunterladen von Code und Eigenschaften im Hintergrund.  
  
-   Benutzeroberfläche active so schnell wie möglich.  
  
-   Berücksichtigen Sie wie persistente Daten gespeichert werden, Eigenschaften und umfangreiche Daten-BLOBs (z. B. eine Bitmap Bild oder ein Video-Daten).  
  
     Steuerelemente mit beträchtliche persistenten Daten, z. B. große Bitmaps oder AVI-Dateien, erfordern besondere Aufmerksamkeit Methode herunterzuladen. Ein Dokument oder eine Seite kann so bald wie möglich angezeigt werden, und ermöglicht dem Benutzer mit der Seite interagieren, während das Abrufen von Daten im Hintergrund durch Steuerelemente.  
  
-   Schreiben Sie effiziente Routinen, mit denen Codegröße und zur Laufzeit nach unten.  
  
     Kleine Schaltfläche und Bezeichnung-Steuerelemente, mit wenigen Bytes persistenten Daten sind für die Internet-Umgebung und die Arbeit in Browsern gut geeignet.  
  
-   Erwägen Sie, dass der Status mitgeteilt wird, auf den Container.  
  
     Teilen Sie dem Container des Status des asynchronen Downloads, einschließlich der Benutzer gestartet werden kann, für die Interaktion mit einer Seite, und der Download abgeschlossen ist. Container kann Fortschritt anzeigen (z. B. % abgeschlossen) für den Benutzer.  
  
-   Erwägen Sie, wie die Steuerelemente auf dem Clientcomputer registriert sind.  
  
## <a name="creating-a-new-activex-control"></a>Erstellen ein neues ActiveX-Steuerelement  
 Wenn Sie ein neues Steuerelement mit dem Assistenten für die Anwendung zu erstellen, können Sie auswählen, um Unterstützung für asynchronen Monikern sowie weiterer Optimierungen zu aktivieren. Gehen Sie folgendermaßen vor, um die Unterstützung zum Herunterladen von Steuerelementeigenschaften asynchron hinzuzufügen:  
  
#### <a name="to-create-your-project-using-the-mfc-activex-control-wizard"></a>Zum Erstellen Ihres Projekts mithilfe von MFC-ActiveX-Steuerelement-Assistenten  
  
1.  Klicken Sie auf `New` auf die **Datei** Menü.  
  
2.  Wählen Sie **MFC-ActiveX-Steuerelement-Assistent** aus der Visual C++-Projekte, und nennen Sie das Projekt.  
  
3.  Auf der **Steuerelementeinstellungen** Seite **lädt Eigenschaften asynchron**. Nach Auswahl dieser Option richtet die Status "bereit"-Eigenschaft und dem Status "bereit" geändert-Ereignis für Sie.  
  
     Sie können auch andere Optimierungen auswählen, z. B. **fensterlose Aktivierung**, das in beschrieben wird [ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md).  
  
4.  Wählen Sie **Fertig stellen** zum Erstellen des Projekts.  
  
#### <a name="to-create-a-class-derived-from-cdatapathproperty"></a>So erstellen Sie eine Klasse von CDataPathProperty abgeleitet  
  
1.  Erstellen Sie eine Klasse abgeleitet `CDataPathProperty`.  
  
2.  Fügen Sie in jedem der Quelldateien, die die Header-Datei für das Steuerelement enthält die Headerdatei für diese Klasse davor hinzu.  
  
3.  In dieser Klasse außer Kraft setzen `OnDataAvailable`. Diese Funktion wird aufgerufen, sobald Daten für die Anzeige verfügbar ist. Sobald Daten verfügbar werden, können Sie es irgendwie behandeln gewählten, z. B. durch progressiv rendern.  
  
     Im folgenden Codeauszug wird progressiv Anzeigen von Daten in ein Bearbeitungssteuerelement über ein einfaches Beispiel. Beachten Sie die Verwendung des Flags **BSCF_FIRSTDATANOTIFICATION** , deaktivieren Sie das Steuerelement zum Bearbeiten.  
  
     [!code-cpp[NVC_MFCActiveXControl#1](../mfc/codesnippet/cpp/activex-controls-on-the-internet_1.cpp)]  
  
     Beachten Sie, dass Sie AFXCMN. H, um mithilfe der `CListCtrl` Klasse.  
  
4.  Wenn Ihre gesamten-Steuerelements Zustand ändert (z. B. von laden zu initialisierten oder interaktiven Benutzer), Aufruf `COleControl::InternalSetReadyState`. Wenn das Steuerelement nur ein Pfad Dateneigenschaft verfügt, können Sie Code hinzufügen, auf **BSCF_LASTDATANOTIFICATION** um dem Container zu benachrichtigen, dass der Download abgeschlossen ist. Zum Beispiel:  
  
     [!code-cpp[NVC_MFCActiveXControl#2](../mfc/codesnippet/cpp/activex-controls-on-the-internet_2.cpp)]  
  
5.  Überschreiben Sie `OnProgress`. In `OnProgress`, übergeben Sie eine Zahl, die den maximalen Bereich und eine Anzahl angezeigte wie weit des aktuellen Downloads entspricht. Diese Nummern können Sie z. B. den Prozentsatz der Fertigstellung Status für den Benutzer anzuzeigen.  
  
 Das nächste Verfahren hinzugefügt Steuerelements angeben, die gerade abgeleitete Klasse eine Eigenschaft.  
  
#### <a name="to-add-a-property"></a>So fügen Sie eine Eigenschaft hinzu  
  
1.  In **Klassenansicht**mit der rechten Maustaste auf die Schnittstelle unterhalb des Bibliotheksknotens, und wählen Sie **hinzufügen**, klicken Sie dann **Eigenschaft hinzufügen**. Dies startet den **Assistent zum Hinzufügen von Eigenschaften**.  
  
2.  In der **Assistent zum Hinzufügen von Eigenschaften**, wählen die **Set/Get-Methoden** Optionsfeld, geben die **Eigenschaftsname**, z. B. EditControlText, und wählen BSTR als die **Eigenschaftentyp**.  
  
3.  Klicken Sie auf **Fertig stellen**.  
  
4.  Deklarieren Sie eine Membervariable des Ihrer `CDataPathProperty`-abgeleitete Klasse, die ActiveX-Steuerelement-Klasse.  
  
     [!code-cpp[NVC_MFCActiveXControl#3](../mfc/codesnippet/cpp/activex-controls-on-the-internet_3.h)]  
  
5.  Implementieren der **Get/Set** Methoden. Für **abrufen**, die Zeichenfolge zurück. Für `Set`, laden Sie die Eigenschaft und der Aufruf `SetModifiedFlag`.  
  
     [!code-cpp[NVC_MFCActiveXControl#4](../mfc/codesnippet/cpp/activex-controls-on-the-internet_4.cpp)]  
  
6.  In [DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange), fügen Sie die folgende Zeile hinzu:  
  
     [!code-cpp[NVC_MFCActiveXControl#5](../mfc/codesnippet/cpp/activex-controls-on-the-internet_5.cpp)]  
  
7.  Überschreiben Sie [Sie ResetData](../mfc/reference/cdatapathproperty-class.md#resetdata) benachrichtigen Sie die Eigenschaft, die das Steuerelement zurückzusetzen, indem Sie die folgende Zeile hinzufügen:  
  
     [!code-cpp[NVC_MFCActiveXControl#6](../mfc/codesnippet/cpp/activex-controls-on-the-internet_6.cpp)]  
  
## <a name="deciding-whether-to-derive-from-cdatapathproperty-or-ccacheddatapathproperty"></a>Entscheidungshilfe für das Ableiten von CDataPathProperty oder CCachedDataPathProperty  
 Im vorherige Beispiel beschreibt die Schritte zum Ableiten der Steuerelementeigenschaft aus `CDataPathProperty`. Dies ist eine gute Wahl, wenn Sie Daten in Echtzeit herunterladen, sich häufig ändert, und für die Sie müssen nicht alle Daten, aber nur der aktuelle Wert beibehalten. Ein Beispiel ist ein Börsenticker-Steuerelement.  
  
 Sie können auch aus ableiten `CCachedDataPathProperty`. In diesem Fall werden die heruntergeladenen Daten in einer Arbeitsspeicherdatei zwischengespeichert. Dies ist eine gute Wahl, wenn Sie die heruntergeladenen Daten behalten müssen – beispielsweise ein Steuerelement, das eine Bitmap progressiv rendert. In diesem Fall verfügt die Klasse eine Membervariable, die Ihre Daten enthält:  
  
 `CMemFile m_Cache;`  
  
 In der ActiveX-Steuerelementklasse, können Sie diese Datei mit zugeordnetem Speicher in `OnDraw` zum Anzeigen der Daten. In das ActiveX-Steuerelement `CCachedDataPathProperty`-abgeleiteten Klasse außer Kraft setzen die Memberfunktion `OnDataAvailable` und das Steuerelement nach dem Aufrufen der basisklassenimplementierung für ungültig zu erklären.  
  
 [!code-cpp[NVC_MFCActiveXControl#7](../mfc/codesnippet/cpp/activex-controls-on-the-internet_7.cpp)]  
  
## <a name="downloading-data-asynchronously-using-activex-controls"></a>Herunterladen von Daten, die asynchron mit ActiveX-Steuerelemente  
 Herunterladen von Daten über ein Netzwerk sollte asynchron erfolgen. Der Vorteil dieser Vorgehensweise ist daher, dass eine große Datenmenge übertragen wird, oder wenn die Verbindung langsam ist, wird der Downloadvorgang nicht andere Prozesse auf dem Client blockiert.  
  
 Asynchrone Moniker bieten eine Möglichkeit zum Herunterladen von Daten asynchron über ein Netzwerk. Ein Lesevorgang für eine asynchrone Moniker gibt sofort zurück, auch wenn der Vorgang nicht abgeschlossen wurde.  
  
 Beispielsweise nur 10 Byte verfügbar sind, und Lesen für eine Datei 1 KB asynchron aufgerufen wird, Lesen nicht blockiert, jedoch mit den derzeit verfügbaren 10 Bytes zurückgibt.  
  
 Implementieren Sie [asynchronen Monikern](../mfc/asynchronous-monikers-on-the-internet.md) mithilfe der `CAsyncMonikerFile` Klasse. ActiveX-Steuerelemente können jedoch die `CDataPathProperty` -Klasse, die abgeleitet ist `CAsyncMonikerFile`, damit die asynchrone Steuerelementeigenschaften zu implementieren.  
  
 Die ASYNDOWN-Beispiel veranschaulicht das Einrichten einer asynchronen Schleife Zeitgeber verwenden, um die Daten zu lesen. ASYNDOWN wird ausführlich beschrieben unter "So wird's gemacht: AsyncDown veranschaulicht asynchrone Herunterladen von Daten" (Q177244) Knowledge Base-Artikel und für den Download im Microsoft Download Center verfügbar ist. (Weitere Informationen zum Herunterladen von Dateien aus dem Microsoft Download Center, finden Sie in der Artikel "How to erhalten Microsoft Support-Dateien aus Online Services" (Q119591) in der Microsoft Knowledge Base). Sie finden Knowledge Base-Artikel unter [http://support.microsoft.com/support](http://support.microsoft.com/support).  
  
 Die grundlegende Methode in ASYNDOWN wird einen Zeitgeber festgelegt **CDataPathProperty** , um anzugeben, wenn Daten verfügbar sind. Wenn das Timer-Nachricht empfangen wird, wird die Anwendung in Blöcken von 128 Byte der Daten liest und ein Bearbeitungssteuerelement füllt. Wenn Daten nicht verfügbar ist, wenn die Timer-Nachricht verarbeitet wird, wird der Timer deaktiviert. `OnDataAvailable`aktiviert den Zeitgeber, wenn später weitere Daten empfangen.  
  
## <a name="displaying-a-control-on-a-web-page"></a>Anzeigen eines Steuerelements auf einer Webseite  
 Hier ist ein Beispiel für ein Objekttag und Attribute für das Einfügen eines Steuerelements auf einer Webseite.  
  
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
  
## <a name="updating-an-existing-ole-control-to-use-new-activex-control-features"></a>Aktualisieren eines vorhandenen OLE-Steuerelements zur Verwendung von neuen Funktionen von ActiveX-Steuerelement  
 Wenn OLE-Steuerelements mit einer Version von Visual C++ vor 4.2 erstellt wurde, stehen die Schritte, die Sie ergreifen können, um die Leistung verbessern und seine Funktionen erweitern. Ausführliche Informationen zu diesen Änderungen finden Sie unter [ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md).  
  
 Wenn Sie ein vorhandenes Steuerelement Unterstützung für asynchrone Eigenschaften hinzufügen, müssen Sie die Status "bereit"-Eigenschaft hinzugefügt und die `ReadyStateChange` Ereignis selbst. Fügen Sie den Konstruktor für das Steuerelement hinzu:  
  
 [!code-cpp[NVC_MFCActiveXControl#8](../mfc/codesnippet/cpp/activex-controls-on-the-internet_8.cpp)]  
  
 Aktualisieren Sie den Status "bereit" wie durch Aufrufen von Code heruntergeladen wird [COleControl::InternalSetReadyState](../mfc/reference/colecontrol-class.md#internalsetreadystate). Sie rufen zentral `InternalSetReadyState` stammt aus dem `OnProgress` Überschreiben von `CDataPathProperty`-abgeleitete Klasse.  
  

  
## <a name="see-also"></a>Siehe auch  
 [MFC-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)   
 [Grundlagen der MFC-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)


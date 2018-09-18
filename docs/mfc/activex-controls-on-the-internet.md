---
title: ActiveX-Steuerelemente für das Internet | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [MFC], creating
- ActiveX controls [MFC], Internet
- downloading data with ActiveX controls
- OLE controls [MFC], upgrading to ActiveX
- Internet applications [MFC], ActiveX controls
- networks [MFC], downloading with ActiveX controls
ms.assetid: 7ab943c8-2022-41df-9065-d629b616eeec
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d3e7603bfe2074022cdaa0e99024627c32452b46
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072796"
---
# <a name="activex-controls-on-the-internet"></a>ActiveX-Steuerelemente für das Internet

ActiveX-Steuerelemente sind die aktualisierte Version der Spezifikation OLE-Steuerelement. 

>[!IMPORTANT]
> ActiveX ist eine veraltete Technologie, die nicht für Neuentwicklungen verwendet werden soll. Weitere Informationen finden Sie unter [ActiveX-Steuerelemente](activex-controls.md).

Steuerelemente sind eine primäre Architektur für die Entwicklung von programmierbaren Softwarekomponenten, die in einer Vielzahl von verschiedenen Containern, einschließlich COM-fähigen Webbrowser, über das Internet verwendet werden können. Alle ActiveX-Steuerelement kann ein Internet Steuerelement und kann der Funktionsumfang eines aktiven Dokuments oder Teil einer Webseite. Steuerelemente auf einer Webseite können mithilfe von Skripts miteinander kommunizieren.  
  
 ActiveX-Steuerelemente sind nicht auf das Internet beschränkt. Ein ActiveX-Steuerelement kann auch in jedem Container verwendet werden, solange das Steuerelement die Schnittstellen erforderlich, die für diesen Container unterstützt.  
  
 **ActiveX-Steuerelemente verwenden mehrere Vorteile, u.a.:**  
  
-   Weniger erforderlichen Schnittstellen als vorherige OLE-Steuerelemente.  
  
-   Die Möglichkeit, die nicht fensterlos sein und immer direkt aktiv.  
  
 **Damit ein ActiveX-Steuerelement werden zu können, müssen ein Steuerelement:**  
  
-   Unterstützung der `IUnknown` Schnittstelle.  
  
-   Ein COM-Objekt sein.  
  
-   Exportieren Sie **DLLRegisterServer** und **DLLUnRegisterServer**.  
  
-   Unterstützen Sie zusätzliche Schnittstellen, wie für die Funktionalität erforderlich.  
  
## <a name="making-your-existing-controls-internet-friendly"></a>Wie werden vorhandene Steuerelemente für das Internet geeignet  
 Entwerfen ein Steuerelement, das in einer Internet-Umgebung gut funktioniert, muss berücksichtigt werden den relativ niedrigen Übertragungsraten im Internet. Sie können Ihre vorhandenen Steuerelemente verwenden. Es gibt jedoch Maßnahmen, die Größe Ihres Codes zu verkleinern und Ihre Eigenschaften asynchron herunterladen sollten.  
  
 Führen Sie zur Verbesserung der Leistung der Steuerelemente diese Tipps zur Effizienz Aspekte aus:  
  
-   Implementieren Sie in diesem Artikel beschriebenen Techniken [ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md).  
  
-   Beachten Sie, wie ein Steuerelement instanziiert wird.  
  
-   Asynchron sein; nicht von anderen Programmen zu halten.  
  
-   Herunterladen von Daten in kleine Blöcke.  
  
     Beim Herunterladen von große Datenströme, z. B. Bitmaps oder Videodaten Zugriff auf die Daten asynchron in Zusammenarbeit mit dem Container eines Steuerelements. Ruft die Daten auf inkrementell oder progressive Weise arbeiten gemeinsam mit anderen Steuerelementen, die auch die Daten abgerufen werden können. Code kann auch asynchron heruntergeladen werden.  
  
-   Herunterladen von Code und die Eigenschaften im Hintergrund.  
  
-   Benutzeroberfläche aktiv ist, so schnell wie möglich.  
  
-   Berücksichtigen Sie wie persistente Daten gespeichert werden, sowohl Eigenschaften als auch umfangreiche Daten-BLOBs (z. B. ein Bild oder Video Bitmapdaten).  
  
     Steuerelemente mit persistenten Daten, z. B. große Bitmaps oder AVI-Dateien an erfordern sorgfältig auf die Download-Methode. Ein Dokument oder eine Seite kann so bald wie möglich sichtbar, und ermöglicht dem Benutzer, die mit der Seite interagieren, während Steuerelemente die Daten im Hintergrund abgerufen.  
  
-   Schreiben Sie effizientere Routinen, mit denen Codegröße und zur Laufzeit nach unten.  
  
     Kleine Schaltfläche und Label-Steuerelemente, mit nur wenigen Bytes des persistenten Daten, eignen sich für die Verwendung in der Internet-Umgebung und die Arbeit auch im Browser.  
  
-   Beachten Sie, dass der Status in den Container übermittelt werden.  
  
     Benachrichtigt den Container des Status des asynchronen Downloads, einschließlich der Benutzer für die Interaktion mit einer Seite beginnen kann, und der Download abgeschlossen ist. Der Container kann Fortschritt anzeigen (z. B. der Fortschritt in Prozent) an den Benutzer.  
  
-   Beachten Sie, wie die Steuerelemente auf dem Clientcomputer registriert sind.  
  
## <a name="creating-a-new-activex-control"></a>Erstellen ein neues ActiveX-Steuerelement  
 Wenn Sie ein neues Steuerelement mit dem Assistenten zum Erstellen, können Sie auswählen, um Unterstützung für asynchrone Moniker sowie weitere Optimierungen zu aktivieren. Um Support, um die Eigenschaften von Steuerelementen asynchron herunterladen hinzuzufügen, gehen Sie folgendermaßen vor:  
  
#### <a name="to-create-your-project-using-the-mfc-activex-control-wizard"></a>Zum Erstellen Ihres Projekts mithilfe von MFC-ActiveX-Steuerelement-Assistenten  
  
1.  Klicken Sie auf **neu** auf die **Datei** Menü.  
  
2.  Wählen Sie **MFC-ActiveX-Steuerelement-Assistent** aus der Visual C++-Projekte, und benennen Sie Ihr Projekt.  
  
3.  Auf der **Steuerelementeinstellungen** Seite **lädt Eigenschaften asynchron**. Nach Auswahl dieser Option richtet die Status "bereit"-Eigenschaft und den Status "bereit" geändert-Ereignis für Sie.  
  
     Sie können auch andere Optimierungen auswählen, wie z. B. **Fensterloser Aktivierung**, das in erläutert wird [ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md).  
  
4.  Wählen Sie **Fertig stellen** zum Erstellen des Projekts.  
  
#### <a name="to-create-a-class-derived-from-cdatapathproperty"></a>Zum Erstellen einer Klasse abgeleitet CDataPathProperty  
  
1.  Erstellen Sie eine Klasse, die von abgeleiteten `CDataPathProperty`.  
  
2.  Fügen Sie in jeder der Quelldateien, die die Header-Datei für das Steuerelement enthält die Headerdatei für diese Klasse vor.  
  
3.  In dieser Klasse außer Kraft setzen `OnDataAvailable`. Diese Funktion wird aufgerufen, wenn die Daten für die Anzeige verfügbar sind. Wenn Daten verfügbar sind, können Sie es beliebig verarbeiten gewählten, z. B. durch progressiv rendern.  
  
     Im folgenden Codeauszug wird ein einfaches Beispiel für schrittweise Anzeige von Daten in einem Bearbeitungssteuerelement. Beachten Sie die Verwendung des Flags **BSCF_FIRSTDATANOTIFICATION** , deaktivieren Sie das Steuerelement zum Bearbeiten.  
  
     [!code-cpp[NVC_MFCActiveXControl#1](../mfc/codesnippet/cpp/activex-controls-on-the-internet_1.cpp)]  
  
     Beachten Sie, dass Sie AFXCMN. H, um Sie verwenden die `CListCtrl` Klasse.  
  
4.  Wenn das Steuerelement insgesamt ist Zustandsänderungen (z. B. von laden zu initialisiert oder interaktive Benutzer), Aufruf `COleControl::InternalSetReadyState`. Wenn das Steuerelement nur eine Path-Eigenschaft verfügt, können Sie Code hinzufügen, auf **BSCF_LASTDATANOTIFICATION** um dem Container zu benachrichtigen, dass der Download abgeschlossen ist. Zum Beispiel:  
  
     [!code-cpp[NVC_MFCActiveXControl#2](../mfc/codesnippet/cpp/activex-controls-on-the-internet_2.cpp)]  
  
5.  Überschreiben Sie `OnProgress`. In `OnProgress`, übergeben Sie eine Zahl, die den maximalen Bereich und eine Anzahl zeigt, wie weit in des aktuellen Downloads ist. Sie können diese Zahlen verwenden, um den Status wie z. B. den Prozentsatz der Fertigstellung an den Benutzer anzuzeigen.  
  
 Die nächste Prozedur fügt eine Eigenschaft für das Steuerelement gerade abgeleitete Klasse zu verwenden.  
  
#### <a name="to-add-a-property"></a>Zum Hinzufügen einer Eigenschaft  
  
1.  In **Klassenansicht**mit der rechten Maustaste auf die sich unter dem Bibliotheksknoten-Schnittstelle, und wählen Sie **hinzufügen**, klicken Sie dann **Eigenschaft hinzufügen**. Dies startet den **Assistent zum Hinzufügen von Eigenschaften**.  
  
2.  In der **Assistent zum Hinzufügen von Eigenschaften**, wählen die **Set/Get-Methoden** Optionsfeld, geben die **Eigenschaftennamen**, z. B. EditControlText, und wählen BSTR als die **Eigenschaftentyp**.  
  
3.  Klicken Sie auf **Fertig stellen**.  
  
4.  Deklarieren Sie eine Membervariable des Ihre `CDataPathProperty`-abgeleiteten Klasse in der ActiveX-Steuerelementklasse.  
  
     [!code-cpp[NVC_MFCActiveXControl#3](../mfc/codesnippet/cpp/activex-controls-on-the-internet_3.h)]  
  
5.  Implementieren Sie die `Get/Set`-Methoden. Für `Get`, die Zeichenfolge zurück. Für `Set`, laden Sie die Eigenschaft und der Aufruf `SetModifiedFlag`.  
  
     [!code-cpp[NVC_MFCActiveXControl#4](../mfc/codesnippet/cpp/activex-controls-on-the-internet_4.cpp)]  
  
6.  In [DoPropExchange](../mfc/reference/colecontrol-class.md#dopropexchange), fügen Sie die folgende Zeile hinzu:  
  
     [!code-cpp[NVC_MFCActiveXControl#5](../mfc/codesnippet/cpp/activex-controls-on-the-internet_5.cpp)]  
  
7.  Außer Kraft setzen [Sie ResetData](../mfc/reference/cdatapathproperty-class.md#resetdata) benachrichtigen Sie die Eigenschaft, die das Steuerelement zurücksetzen, indem Sie diese Zeile:  
  
     [!code-cpp[NVC_MFCActiveXControl#6](../mfc/codesnippet/cpp/activex-controls-on-the-internet_6.cpp)]  
  
## <a name="deciding-whether-to-derive-from-cdatapathproperty-or-ccacheddatapathproperty"></a>Entscheiden, ob Sie von CDataPathProperty oder CCachedDataPathProperty abgeleitet werden  
 Im vorherige Beispiel beschreibt die Schritte zum Ableiten des Steuerelements-Eigenschaft von `CDataPathProperty`. Dies ist eine gute Wahl, wenn Sie Daten in Echtzeit heruntergeladen haben, sich häufig ändert, und für die Sie müssen nicht alle Daten, aber nur der aktuelle Wert beibehalten. Ein Beispiel ist ein Börsenticker-Steuerelement.  
  
 Sie können auch Ableiten aus `CCachedDataPathProperty`. In diesem Fall werden die heruntergeladenen Daten in einer Arbeitsspeicherdatei zwischengespeichert. Dies ist eine gute Wahl, wenn Sie alle heruntergeladene Daten beibehalten möchten, z. B. ein Steuerelement, das eine Bitmap progressiv rendert. In diesem Fall verfügt die Klasse eine Membervariable, die mit den Daten:  
  
 `CMemFile m_Cache;`  
  
 In der ActiveX-Steuerelementklasse, können Sie diese Datei mit zugeordnetem Speicher in `OnDraw` zum Anzeigen der Daten. In das ActiveX-Steuerelement `CCachedDataPathProperty`-abgeleiteten Klasse außer Kraft setzen die Memberfunktion `OnDataAvailable` und das Steuerelement, nach dem Aufruf der basisklassenimplementierung ungültig.  
  
 [!code-cpp[NVC_MFCActiveXControl#7](../mfc/codesnippet/cpp/activex-controls-on-the-internet_7.cpp)]  
  
## <a name="downloading-data-asynchronously-using-activex-controls"></a>Herunterladen von Daten, die asynchron mit ActiveX-Steuerelemente  
 Herunterladen von Daten über ein Netzwerk sollten asynchron durchgeführt werden. Der Vorteil dieser Vorgehensweise ist, also, sofern eine große Datenmenge übertragen wird, oder wenn die Verbindung langsam ist, der Downloadprozess nicht andere Prozesse auf dem Client blockiert.  
  
 Asynchrone Moniker bieten eine Möglichkeit zum Herunterladen von Daten asynchron über ein Netzwerk. Ein Lesevorgang für eine asynchrone Moniker gibt sofort zurück, selbst wenn der Vorgang nicht abgeschlossen wurde.  
  
 Beispielsweise nur 10 Bytes verfügbar sind, und Lesen für eine 1-KB-Datei asynchron aufgerufen wird, Lesen nicht blockiert, jedoch mit den derzeit verfügbaren 10 Bytes zurückgibt.  
  
 Implementieren Sie [asynchronen Monikern](../mfc/asynchronous-monikers-on-the-internet.md) mithilfe der `CAsyncMonikerFile` Klasse. ActiveX-Steuerelemente können jedoch die `CDataPathProperty` -Klasse, die abgeleitet wird `CAsyncMonikerFile`, damit die asynchronen Eigenschaften implementieren.  
  
 Das ASYNDOWN demonstriert das Einrichten einer asynchronen Schleife Timer zum Lesen der Daten verwenden. ASYNDOWN ist ausführlich im Knowledge Base-Artikel "So wird's gemacht: AsyncDown veranschaulicht asynchrone Herunterladen von Daten" (Q177244) und steht zum Download aus dem Microsoft Download Center. (Weitere Informationen zum Herunterladen von Dateien aus dem Microsoft Download Center finden Sie im "Wie auf erhalten Microsoft Support-Dateien aus Online Services" (Q119591) in der Microsoft Knowledge Base-Artikel.) Sie finden Knowledge Base-Artikel unter [ http://support.microsoft.com/support ](http://support.microsoft.com/support).  
  
 Die grundlegende Technik in ASYNDOWN verwendet wird, legen Sie einen Timer in **CDataPathProperty** , um anzugeben, wenn Daten verfügbar sind. Wenn die Timer-Nachricht empfangen wird, wird die Anwendung liest die 128-Byte-Blöcken der Daten und füllt eine Bearbeitungssteuerelement. Wenn Daten nicht verfügbar ist, wenn die Timer-Nachricht verarbeitet wird, wird der Zeitgeber deaktiviert. `OnDataAvailable` aktiviert den Zeitgeber, falls später weitere Daten empfangen.  
  
## <a name="displaying-a-control-on-a-web-page"></a>Anzeigen eines Steuerelements auf einer Webseite  
 Hier ist ein Beispiel für ein Object-Tag und die Attribute für das Einfügen eines Steuerelements auf einer Webseite ein.  
  
```xml
<OBJECT
  CLASSID="clsid:FC25B780-75BE-11CF-8B01-444553540000"
  CODEBASE="/ie/download/activex/iechart.ocx"
  ID=chart1
  WIDTH=400
  HEIGHT=200
  ALIGN=center
  HSPACE=0
  VSPACE=0>
  <PARAM NAME="BackColor" value="#ffffff"/>
  <PARAM NAME="ForeColor" value="#0000ff"/>
  <PARAM NAME="url" VALUE="/ie/controls/chart/mychart.txt"/>
</OBJECT>
```
  
## <a name="updating-an-existing-ole-control-to-use-new-activex-control-features"></a>Aktualisieren eines bestehenden OLE-Steuerelements zur Verwendung von neuen Funktionen von ActiveX-Steuerelement  
 Wenn das OLE-Steuerelement mit einer Version von Visual C++ vor 4.2 erstellt wurde, stehen die Schritte, die Sie ergreifen können, die die Leistung verbessern und Erweitern der Funktionalität. Eine ausführliche Erläuterung dieser Änderungen, finden Sie unter [ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md).  
  
 Wenn Sie Unterstützung für asynchrone Eigenschaften auf ein vorhandenes Steuerelement hinzufügen, müssen Sie die Status "bereit" Eigenschaft hinzufügen und die `ReadyStateChange` Ereignis selbst. Fügen Sie im Konstruktor für das Steuerelement Folgendes hinzu:  
  
 [!code-cpp[NVC_MFCActiveXControl#8](../mfc/codesnippet/cpp/activex-controls-on-the-internet_8.cpp)]  
  
 Aktualisieren Sie den Status "bereit" während des Downloads des Codes durch den Aufruf [COleControl::InternalSetReadyState](../mfc/reference/colecontrol-class.md#internalsetreadystate). Sie rufen zentral `InternalSetReadyState` stammt aus der `OnProgress` Überschreiben von `CDataPathProperty`-abgeleitete Klasse.  
  

  
## <a name="see-also"></a>Siehe auch  
 [MFC-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)   
 [Grundlagen der MFC-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)


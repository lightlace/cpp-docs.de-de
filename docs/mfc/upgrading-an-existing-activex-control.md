---
title: "Upgrading eines vorhandenen ActiveX-Steuerelements"
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
  - "ActiveX-Steuerelemente [C++], Internet"
  - "CAB-Dateien, Für ActiveX-Steuerelemente"
  - "Internetanwendungen [C++], ActiveX-Steuerelemente"
  - "Internetanwendungen [C++], Verpacken von Code zum Herunterladen"
  - "Lizenzieren von ActiveX-Steuerelementen"
  - "LPK_Dateien für Internetsteuerelemente"
  - "OLE-Steuerelemente [C++], Upgrade auf ActiveX"
  - "Speichern für Skripting und Initialisierung (Steuerelemente)"
  - "Aktualisieren von ActiveX-Steuerelementen"
ms.assetid: 4d12ddfa-b491-4f9f-a0b7-b51458e05651
caps.latest.revision: 15
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Upgrading eines vorhandenen ActiveX-Steuerelements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vorhandene ActiveX\-Steuerelemente \(früher OLE\-Steuerelemente\) sind im Internet ohne Änderungen verwendet werden.  Sie sollten Steuerelemente ändern, um ihre Leistung zu verbessern.  Wenn Sie das Steuerelement auf einer Webseite verwendet wird, gibt es weitere Überlegungen.  Die OCX\-Datei und alle unterstützenden Dateien müssen auf dem Zielcomputer sein oder über das Internet heruntergeladen werden.  Dies macht Codegröße und Downloadzeit einen wichtigen Aspekt.  Downloads können in eine CAB\-Datei gepackt sind mit Vorzeichen.  Sie können das Steuerelement als sicher für die Skripterstellung und als sicher für das Initialisieren markieren.  
  
 In diesem Artikel werden die folgenden Themen:  
  
-   [Verpackencode zum Herunterladen](#_core_packaging_code_for_downloading)  
  
-   [Markieren eines Steuersafes für die Skripterstellung und Initialisieren](#_core_marking_a_control_safe_for_scripting_and_initializing)  
  
-   [Lizenzierungs\-Probleme](#_core_licensing_issues)  
  
-   [Signieren von Code](#_core_signing_code)  
  
-   [Verwalten der Palette](#_core_managing_the_palette)  
  
-   [Internet Explorer\-Browser\-Sicherheits\-Ebenen und Steuerelementverhalten](#_core_internet_explorer_browser_safety_levels_and_control_behavior)  
  
 Sie können auch Optimierungen hinzufügen, wie in [ActiveX\-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md) beschrieben.  Moniker können verwendet werden, um Eigenschaften und große Blobs asynchron herunterzuladen, wie in [ActiveX\-Steuerelemente im Internet](../mfc/activex-controls-on-the-internet.md) beschrieben.  
  
##  <a name="_core_packaging_code_for_downloading"></a> Verpackencode zum Herunterladen  
 Weitere Informationen zu diesem Thema, finden Sie die Verpackenmfc Steuerelemente für Knowledge Base\-Artikel\-" zur Verwendung über das Internet \(" Q167158\).  Knowledge Base\-Artikel finden Sie auf der MSDN Library\-CD\-ROM oder unter [http:\/\/support.microsoft.com\/support](http://support.microsoft.com/support).  
  
### Das CODEBASE Tag  
 ActiveX\-Steuerelemente sind in den Webseiten mit Tags des `<OBJECT>` eingebettet.  Der `CODEBASE`\-Parameter des `<OBJECT>`\-Tags gibt den Speicherort an, von dem das Steuerelement herunterladen.  `CODEBASE` kann sich an verschiedenen Dateitypen erfolgreich zeigen.  
  
### Verwenden des CODEBASE Tags mit OCX\-Datei  
  
```  
CODEBASE="http://example.microsoft.com/mycontrol.ocx#version=4,70,0,1086"  
```  
  
 Diese Lösung lädt nur die OCX\-Datei des Steuerelements herunter und erfordert alle unterstützenden DLLs, auf dem Clientcomputer bereits installiert werden.  Dies funktioniert für Internet Explorer und MFC\-ActiveX\-Steuerelemente, die mit Visual C\+\+, da Internet Explorer\-Schiffe mit den zugehörigen DLLs für Visual C\+\+\-Kontrollen erstellt werden.  Wenn ein anderer Internetbrowser, der Steuerelement\-fähiges ActiveX ist, verwendet wird, um dieses Steuerelement anzuzeigen, funktioniert diese Projektmappe nicht.  
  
### Verwenden des CODEBASE Tags mit einer INF\-Datei  
  
```  
CODEBASE="http://example.microsoft.com/trustme.inf"  
```  
  
 Eine INF\-Datei steuert die Installation eines .ocx und der unterstützenden Dateien.  Diese Methode wird nicht empfohlen, da es nicht möglich ist, eine INF\-Datei zu signieren \(siehe [Signieren von Code](#_core_signing_code) für Zeiger auf Codesignaturen\).  
  
### Verwenden der CODEBASE kennzeichnen Sie eine CAB\-Datei  
  
```  
CODEBASE="http://example.microsoft.com/acontrol.cab#version=1,2,0,0"  
```  
  
 CAB\-Dateien sind die empfohlene Methode, ActiveX\-Steuerelementen erstellen, die MFC verwenden.  Das Verpacken eines MFC\-ActiveX\-Steuerelements in eine CAB\-Datei können, um eine Installation enthalten werden, INF\-Datei des ActiveX\-Steuerelements und aller abhängigen DLLs zu steuern \(z der MFC\-DLLs\).  Verwenden einer CAB\-Datei komprimiert automatisch den Code für einen schnelleren Download.  Wenn Sie eine CAB\-Datei für Teildownload verwenden, befindet er schneller, die CAB\-Datei gesamte als jede einzelne Komponente zu signieren.  
  
### Erstellen von CAB\-Dateien  
 Sie können das Gehäuse\-Entwicklungs\-Kit aus dem Knowledge Base\-Artikel herunterladen [310618: Microsoft\-Gehäuse\-Software Development Kit](http://go.microsoft.com/fwlink/?LinkId=148204).  In diesem Kit suchen die erforderlichen Tools, um CAB\-Dateien zu erstellen.  
  
 CAB\-Datei, auf die `CODEBASE` zeigt, sollte die OCX\-Datei enthalten, die das ActiveX\-Steuerelement und eine INF\-Datei ihre Installation gesteuert.  Sie erstellen die CAB\-Datei, indem Sie den Namen der Datei des Benutzersteuerelements und der INF\-Datei angeben.  Fügen Sie keine abhängigen DLLs ein, die möglicherweise bereits vom System in dieser CAB\-Datei vorhanden sind.  Beispielsweise werden die MFC\-DLLs in einer separaten CAB\-Datei gepackt und angegeben durch die steuernde INF\-Datei.  
  
 Ausführliche Informationen, wie eine CAB\-Datei erstellen, finden Sie unter [Erstellen eine CAB\-Datei](assetId:///cc52fd09-bdf6-4410-a693-149a308f36a3).  
  
### Die INF\-Datei  
 Im folgenden Beispiel, spindial.inf, Listen die unterstützenden Dateien und Versionsinformationen die für das Steuerelement Spindial MFC.  Beachten Sie den Speicherort für die MFC\-DLLs ist eine Microsoft\-Website.  Das mfc42.cab wird von Microsoft zur Verfügung gestellt und signiert.  
  
```  
Contents of spindial.inf:  
[mfc42installer]   
file-win32-x86=http://activex.microsoft.com/controls/vc/mfc42.cab   
[Olepro32.dll] - FileVersion=5,0,4261,0  
[Mfc42.dll] - FileVersion=6,0,8168,0  
[Msvcrt.dll] - FileVersion=6,0,8168,0  
```  
  
### Das \<OBJEKT\>\-Tag  
 Im folgenden Beispiel wird mithilfe des `<OBJECT>`\-Tags, das Steuerelement Spindial zu verpacken Beispiel. MFC  
  
```  
<OBJECT ID="Spindial1" WIDTH=100 HEIGHT=51  
  CLASSID="CLSID:06889605-B8D0-101A-91F1-00608CEAD5B3"  
  CODEBASE="http://example.microsoft.com/spindial.cab#Version=1,0,0,001">  
    <PARAM NAME="_Version" VALUE="65536">  
    <PARAM NAME="_ExtentX" VALUE="2646">  
    <PARAM NAME="_ExtentY" VALUE="1323">  
    <PARAM NAME="_StockProps" VALUE="0">  
    <PARAM NAME="NeedlePosition" VALUE="2">  
</OBJECT>  
```  
  
 In diesem Fall enthält spindial.cab zwei Dateien, spindial.ocx und spindial.inf.  Der folgende Befehl erstellt die CAB\-Datei:  
  
```  
C:\CabDevKit\cabarc.exe -s 6144 N spindial.cab spindial.ocx spindial.inf   
```  
  
 Das `–s 6144`\-Parameterreservenleerzeichen im Gehäuse für Codesignaturen.  
  
### Das Versions\-Tag  
 Beachten Sie hier, dass die `#Version` \- Informationen, die einer CAB\-Datei angegeben werden, auf das Steuerelement angewendet werden, das durch den `CLASSID` des Tags Parameter `<OBJECT>` angegeben wird.  
  
 Abhängig von der angegebenen Version, können Sie erzwingen Download des Steuerelements.  Ausführliche Spezifikation des `OBJECT`\-Tags einschließlich den Parameter `CODEBASE`, finden Sie den W3C\-Verweis.  
  
##  <a name="_core_marking_a_control_safe_for_scripting_and_initializing"></a> Markieren eines Steuersafes für die Skripterstellung und Initialisieren  
 ActiveX\-Steuerelemente, die auf Webseiten verwendet werden, sollten als sicher für die Skripterstellung und Sicherheit für das Initialisieren markiert werden, wenn sie tatsächlich sicher sind.  Ein sicheres Steuerelement führt keine Datenträger EA aus oder greift den Arbeitsspeicher oder auf die Register eines Computers direkt zu.  
  
 Steuerelemente können als sicher für die Skripterstellung und Sicherheit für das Initialisieren zur Registrierung markiert werden.  Ändern Sie `DllRegisterServer`, um die Einträge hinzuzufügen, die zum folgenden, um das Steuerelement als sicher für die Skripterstellung und Dauerhaftigkeit in der Registrierung zu markieren.  Eine alternative Methode besteht darin, `IObjectSafety` zu implementieren.  
  
 Sie definieren GUIDs \(Globally Unique Identifier\) für das Steuerelement, um es zu markieren sicher für die Skripterstellung und zur Beibehaltung.  Steuerelemente, die sicher auf Skriptbasis erstellt werden können, enthalten einen Registrierungseintrag, der ähnlich dem folgenden ist:  
  
```  
HKEY_CLASSES_ROOT\Component Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}  
```  
  
 Steuerelemente, die mit persistenten Daten sicher initialisiert werden können, sind als sicher zur Beibehaltung mit einen Registrierungseintrag, der zu ähnlich ist:  
  
```  
HKEY_CLASSES_ROOT\Component Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}  
```  
  
 Fügen Sie die Einträge hinzu, die zum folgenden ähneln \(die Klassen\-ID des Steuerelements und `{06889605-B8D0-101A-91F1-00608CEAD5B3}` ersetzen\) um die Tasten mit der folgenden ein Klassenbezeichner zuzuweisen:  
  
```  
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}   
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}   
```  
  
##  <a name="_core_licensing_issues"></a> Lizenzierungs\-Probleme  
 Wenn Sie ein lizenziertes Steuerelement auf einer Webseite verwenden möchten, müssen Sie überprüfen, ob der Softwarelizenzvertrag seine Verwendung im Internet erlaubt und erstellen eine Lizenzpaketdatei \(LPK\) für sie.  
  
 Ein lizenziertes ActiveX\-Steuerelement lädt nicht ordnungsgemäß in einer HTML\-Seite, wenn der Computer, der Internet Explorer ausführt, nicht lizenziert wird, um das Steuerelement zu verwenden.  Ein lizenziertes Steuerelement mit Visual C\+\+ erstellt wurde, lädt die HTML\-Seite mithilfe des Steuerelements korrekt auf dem Computer, auf dem das Steuerelement erstellt wurde, jedoch nicht geladen auf einem anderen Computer, sofern, Informationen lizenzierend, wird einbezogen.  
  
 Um ein lizenziertes ActiveX\-Steuerelement in Internet Explorer zu verwenden, müssen Sie die Lizenzvereinbarung des Anbieters überprüfen sicherzustellen dass die Lizenz für das Steuerelement ermöglicht:  
  
-   Verteilung  
  
-   Verwendung vom Steuerelement im Internet  
  
-   Verwendung des CodeBase\-Parameter  
  
 Um ein lizenziertes Steuerelement in einer HTML\-Seite nonlicensed auf einem Computer zu verwenden, müssen Sie eine Lizenzpaketdatei \(LPK\) generieren.  Die LPK\-Datei enthält Ablauflizenzen für lizenzierte Steuerelemente auf der HTML\-Seite.  Diese Datei wird zum LPK\_TOOL.EXE generiert, das dem ActiveX\-SDK stammt.  Weitere Informationen finden Sie auf der MSDN\-Website an [http:\/\/msdn.microsoft.com](http://msdn.microsoft.com).  
  
#### So erstellen Sie eine LPK\-Datei  
  
1.  Führen Sie LPK\_TOOL.EXE auf einem Computer aus, der über wird, um das Steuerelement zu verwenden.  
  
2.  Im Dialogfeld **Lizenzpaketentwicklungstool** im Listenfeld **Verfügbar Steuerelemente**, wählen Sie eines lizenzierte ActiveX\-Steuerelement aus, das auf der HTML\-Seite und dem auf **Hinzufügen** verwendet wird.  
  
3.  Klicken Sie auf  **Save & Exit** und geben Sie einen Namen für die LPK\-Datei ein.  Damit wird die LPK\-Datei und schließt die Anwendung.  
  
#### So ein lizenziertes Steuerelement auf einer HTML\-Seite einbetten  
  
1.  Bearbeiten Sie die HTML\-Seite.  In der HTML\-Seite fügen Sie ein \<OBJEKTtag\> für das Lizenz\-Managerobjekt vor allen anderen \<OBJEKTtags\> ein.  Der Lizenz\-Manager ist ein ActiveX\-Steuerelement, der mit Internet Explorer installiert ist.  Die Klassen\-ID wird unten angezeigt.  Legen Sie die LPKPath\-Eigenschaft des Lizenz\-Managerobjekts den Pfad und den Namen der LPK\-Datei fest.  Sie können nur eine LPK\-Datei pro HTML\-Seite haben.  
  
    ```  
    <OBJECT CLASSID = "clsid:5220cb21-c88d-11cf-b347-00aa00a28331">  
        <PARAM NAME="LPKPath" VALUE="relative URL to .LPK file">  
    </OBJECT>  
    ```  
  
2.  Fügen Sie das \<OBJEKTtag\> für das lizenziertes Steuerelement nach dem Lizenz\-Managertag ein.  
  
     Beispielsweise wird eine HTML\-Seite, die das Microsoft\-MaskedEdit\-Steuerelement anzeigt, unten angezeigt.  Die ID der ersten Klasse ist für das Lizenz\-Managersteuerelement, die zweite Klasse, die ID für das Masked Edit\-Steuerelement ist.  Ändern Sie die Tags, um auf den relativen Pfad der .lpk\-Datei zu zeigen, die Sie zuvor erstellt haben, und fügen Sie einen Objekttag einschließlich die Klassen\-ID für das Steuerelement.  
  
3.  Fügen Sie das \<EINBETTENSattribut\> für die LPK\-Datei ein, wenn Sie das Plug\-In NCompass ActiveX verwenden.  
  
     Wenn das Steuerelement möglicherweise auf anderen aktiven aktivierten Browsern angezeigt wird, beispielsweise Netscape mithilfe des Plug\-Ins NCompass ActiveX \- Sie müssen die \<EINBETTENSsyntax\> wie gezeigt hinzufügen.  
  
    ```  
    <OBJECT CLASSID="clsid:5220cb21-c88d-11cf-b347-00aa00a28331">  
        <PARAM NAME="LPKPath" VALUE="maskedit.lpk">  
  
        <EMBED SRC = "maskedit.LPK">  
  
    </OBJECT>  
    <OBJECT CLASSID="clsid:C932BA85-4374-101B-A56C-00AA003668DC" WIDTH=100 HEIGHT=25>  
    </OBJECT>  
    ```  
  
 Weitere Informationen über Steuerlizenzierung, finden Sie unter [ActiveX\-Steuerelemente: Lizenzieren eines ActiveX\-Steuerelements](../mfc/mfc-activex-controls-licensing-an-activex-control.md).  
  
##  <a name="_core_signing_code"></a> Signieren von Code  
 Codesignaturen sind, um die Quelle des Codes zu identifizieren, konzipiert und sicherzustellen, dass der Code nicht geändert wurde, seitdem es signiert wurde.  Abhängig von Browsersicherheitseinstellungen werden Benutzer möglicherweise gewarnt, bevor der Code heruntergeladen wird.  Benutzer klicken kann, um bestimmten Zertifikatsbesitzern oder \-Unternehmen zu vertrauen, wird der Code, der von vertrauten die signiert wird, heruntergeladen wird, ohne Warnung.  Code ist digital signiert manipuliert werden.  
  
 Stellen Sie sicher, dass das endgültige Code signiert, sodass das Steuerelement automatisch heruntergeladen werden kann, ohne Vertrauenswürdigkeitswarnmeldungen anzuzeigen.  Ausführliche Informationen, wie Code, überprüfen Sie die Dokumentation auf Authenticode im ActiveX\-SDK und finden Sie unter [Signieren einer CAB\-Datei](assetId:///04d8b47a-8f1c-4b54-ab90-730fcdc03747).  
  
 Abhängig von Vertrauenswürdigkeits\- und Browsersicherheitsebeneneinstellungen wird ein Zertifikat werden angezeigt, um die Signierungsperson oder \-Unternehmen zu identifizieren.  Wenn die Sicherheitsebene keine ist oder wenn der Zertifikatsbesitzer des Steuerelements mit Vorzeichen vertrauenswürdig ist, wird ein Zertifikat nicht angezeigt.  [Internet Explorer\-Browser\-Sicherheits\-Ebenen und Steuerelementverhalten](#_core_internet_explorer_browser_safety_levels_and_control_behavior) finden Sie Informationen darüber, wie die Browsersicherheitseinstellung bestimmt, ob das Steuerelement heruntergeladen wird und ein Zertifikat angezeigt.  
  
 Digital\-Signierungsgarantiecode wurde nicht geändert, da es signiert wurde.  Ein Hash des Codes wird im Zertifikat übernommen und eingebettet.  Dieser Hash wird später mit einem Hash des Code Klassen verglichen, nachdem der Code heruntergeladen wurde, jedoch bevor er ausgeführt wird.  Unternehmen wie Verisign können die privaten und öffentlichen Schlüssel bereitstellen, die erforderlich sind, zu signieren.  Die ActiveX\-SDK\-Schiffe mit MakeCert, ein Dienstprogramm zum Erstellen von Testzertifikaten.  
  
##  <a name="_core_managing_the_palette"></a> Verwalten der Palette  
 Container bestimmen die Palette und stellen sie als Ambient\-Eigenschaft, **DISPID\_AMBIENT\_PALETTE** bereit.  Ein Container \(beispielsweise, Internet Explorer\) markiert eine Palette aus, die durch alle ActiveX\-Steuerelemente auf einer Seite verwendet wird, um ihre eigene Palette zu bestimmen.  Dies verhindert die Anzeige flimmernde und stellt eine konsistente Darstellung dar.  
  
 Ein Steuerelement kann `OnAmbientPropertyChange` überschreiben, um Benachrichtigungen über Änderungen der Palette zu bearbeiten.  
  
 Ein Steuerelement kann `OnGetColorSet` überschreiben, um eine Farbpalette zurückgibt, um die Palette zu zeichnen.  Containers verwendet den Rückgabewert, um zu bestimmen, ob ein Steuerelement Palette\-bewusst ist.  
  
 Die Richtlinien OCX 96 muss ein Steuerelement die Palette immer im Hintergrund erkennen.  
  
 Ältere Container, die nicht die Paletteneigenschaft Umgebungspinsel verwenden, `WM_QUERYNEWPALETTE` und `WM_PALETTECHANGED` senden Meldungen.  Ein Steuerelement kann `OnQueryNewPalette` und `OnPaletteChanged` überschreiben, um die Nachrichten behandeln.  
  
##  <a name="_core_internet_explorer_browser_safety_levels_and_control_behavior"></a> Internet Explorer\-Browser\-Sicherheits\-Ebenen und Steuerelementverhalten  
 Ein Browser enthält die Optionen für Sicherheitsebene konfigurierbar, durch den Benutzer.  Da Webseiten aktiven Inhalt enthalten können, der potenziell den Computer eines Benutzers schädigte, lassen Benutzer vom Browser an die ausgewählten Optionen Sicherheitsebene zu.  Je nach Methode implementiert ein Browser Sicherheitsebenen, wird ein Steuerelement möglicherweise nicht vorhanden oder ist anzeigen ein Zertifikat oder eine Warnmeldung, um dem Benutzer ermöglichen, zur Laufzeit auszuwählen heruntergeladen, ob das Steuerelement.  Das Verhalten von ActiveX\-Steuerelementen im hohen, mittleren und grundlegenden Sicherheitsebenen auf Internet Explorer wird unten aufgeführt.  
  
### Hoher Sicherheits\-Modus  
  
-   Steuerelemente ohne Vorzeichen werden nicht heruntergeladen.  
  
-   Steuerelemente mit Vorzeichen enthalten ein Zertifikat, wenn nicht vertrauenswürdig \(ein Benutzer kann eine Option auswählen, Code aus diesem Zertifikatsbesitzer immer ab sofort zu vertrauen\).  
  
-   Nur Steuerelemente, die als sicher markiert wurden, werden dauerhafte Daten und\/oder skriptfähig sind.  
  
### Mittlerer Sicherheits\-Modus  
  
-   Steuerelemente ohne Vorzeichen zeigen eine Warnung an, bevor diese herunterladen.  
  
-   Steuerelemente mit Vorzeichen enthalten ein Zertifikat, wenn nicht vertrauenswürdig.  
  
-   Die Steuerelemente, die nicht als sicher markiert werden, wird eine Warnung an.  
  
### Sicherheits\-Modus Geringer  
  
-   Steuerelemente werden heruntergeladen, ohne Warnung.  
  
-   Skripterstellung und Dauerhaftigkeit treten auf, ohne Warnung.  
  
## Siehe auch  
 [MFC\-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)   
 [Grundlagen der MFC\-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)   
 [MFC\-ActiveX\-Steuerelemente: Lizenzieren eines ActiveX\-Steuerelements](../mfc/mfc-activex-controls-licensing-an-activex-control.md)
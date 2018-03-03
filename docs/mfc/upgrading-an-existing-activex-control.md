---
title: Upgrading eines vorhandenen ActiveX-Steuerelements | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [MFC], Internet
- LPK files for Internet controls
- safe for scripting and initialization (controls)
- OLE controls [MFC], upgrading to ActiveX
- CAB files, for ActiveX controls
- Internet applications [MFC], ActiveX controls
- Internet applications [MFC], packaging code for download
- upgrading ActiveX controls
- licensing ActiveX controls
ms.assetid: 4d12ddfa-b491-4f9f-a0b7-b51458e05651
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1a7b9c76ffd4366522dce366a165698bd3a26173
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="upgrading-an-existing-activex-control"></a>Upgrading eines vorhandenen ActiveX-Steuerelements
Vorhandenen ActiveX-Steuerelementen (früher OLE-Steuerelemente) im Internet, ohne Änderungen verwendet werden können. Allerdings empfiehlt es sich so ändern Sie Steuerelemente, um ihre Leistung zu verbessern. Wenn das Steuerelement auf einer Webseite verwenden, sind weitere Überlegungen. Die Datei ".ocx" und alle unterstützenden Dateien müssen auf dem Zielcomputer sein oder über das Internet heruntergeladen werden. Dadurch wird die Codegröße als auch Download Zeit einen wichtigen Aspekt. Downloads können in einer signierten CAB-Datei verpackt werden. Sie können das Steuerelement als sicher für Skripting und als sicher für die Initialisierung kennzeichnen.  
  
 In diesem Artikel werden die folgenden Themen erläutert:  
  
- [Verpacken von Code zum Herunterladen](#_core_packaging_code_for_downloading)  
  
- [Markieren ein sicheres Steuerelement für Skripting und Initialisierung](#_core_marking_a_control_safe_for_scripting_and_initializing)  
  
- [Lizenzierungsprobleme](#_core_licensing_issues)  
  
- [Signieren von Code](#_core_signing_code)  
  
- [Verwalten der Palette](#_core_managing_the_palette)  
  
- [Internet Explorer-Browser-Sicherheitsstufen und Verhalten des Steuerelements](#_core_internet_explorer_browser_safety_levels_and_control_behavior)  
  
 Sie können auch Optimierungen hinzufügen, wie in beschrieben [ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md). Moniker können verwendet werden, um Eigenschaften herunterladen und asynchron ausgeführt wird, wie beschrieben in große BLOBs [ActiveX-Steuerelemente für das Internet](../mfc/activex-controls-on-the-internet.md).  
  
##  <a name="_core_packaging_code_for_downloading"></a>Verpacken von Code zum Herunterladen  
 Weitere Informationen zu diesem Thema finden Sie unter im Knowledge Base-Artikel "Verpackung MFC-Steuerelemente für die Verwendung über das Internet" (Q167158). Sie finden Knowledge Base-Artikel unter [http://support.microsoft.com/support](http://support.microsoft.com/support).  
  
### <a name="the-codebase-tag"></a>CODEBASE-Tags  
 ActiveX-Steuerelemente sind in Webseiten mit eingebetteten der `<OBJECT>` Tag. Die `CODEBASE` Parameter von der `<OBJECT>` Tag gibt den Speicherort, von denen das Steuerelement heruntergeladen. `CODEBASE`kann auf eine Anzahl von verschiedenen Dateitypen erfolgreich verweisen.  
  
### <a name="using-the-codebase-tag-with-an-ocx-file"></a>Verwenden die CODEBASE-Tags mit einer OCX-Datei  
  
```  
CODEBASE="http://example.microsoft.com/mycontrol.ocx#version=4,
    70,
    0,
    1086"  
```  
  
 Diese Lösung wird nur das Steuerelement ".ocx"-Datei heruntergeladen und verlangt, dass alle unterstützenden DLLs bereits auf dem Clientcomputer installiert sein. Dies funktioniert für Internet Explorer und MFC-ActiveX-Steuerelemente, die mit Visual C++ erstellt, da Internet Explorer mit der unterstützenden DLLs für Visual C++-Steuerelemente geliefert wird. Wenn Sie einen anderen Internetbrowser, die ActiveX-Steuerelement-fähig ist zum Anzeigen dieses Steuerelements verwendet wird, funktioniert diese Lösung nicht.  
  
### <a name="using-the-codebase-tag-with-an-inf-file"></a>Verwenden die CODEBASE-Tags mit einer INF-Datei  
  
```  
CODEBASE="http://example.microsoft.com/trustme.inf"  
```  
  
 Eine INF-Datei wird die Installation von einem ".ocx" und die unterstützenden Dateien steuern. Diese Methode wird nicht empfohlen, da es nicht möglich, eine INF-Datei zu signieren, ist (siehe [Signieren von Code](#_core_signing_code) für Zeiger auf das Signieren von Code).  
  
### <a name="using-the-codebase-tag-with-a-cab-file"></a>Verwenden die CODEBASE-Tags mit einer CAB-Datei  
  
```  
CODEBASE="http://example.microsoft.com/acontrol.cab#version=1,
    2,
    0,
    0"  
```  
  
 CAB-Dateien sind die empfohlene Methode zum Paket ActiveX-Steuerelemente, die MFC verwenden. Ein MFC-ActiveX-Steuerelement in einer CAB-Datei verpacken ermöglicht eine INF-Datei mit der die Installation von ActiveX-Steuerelement und alle abhängigen DLLs (z. B. die MFC-DLLs) eingeschlossen werden sollen. Verwenden eine CAB-Datei automatisch komprimiert den Code schneller herunterladen. Wenn Sie eine CAB-Datei für den Download der Komponenten verwenden, ist es schneller, um die gesamte CAB-Datei anstelle der einzelnen Komponenten zu signieren.  
  
### <a name="creating-cab-files"></a>Erstellen von CAB-Dateien  
 Sie können die CAB-Datei Development Kit herunterladen, aus dem Knowledge Base-Artikel [310618: Microsoft CAB-Datei Software Development Kit](http://go.microsoft.com/fwlink/p/?linkid=148204). In diesem Kit finden Sie die erforderlichen Tools zum Erstellen von CAB-Dateien.  
  
 Die CAB-Datei verweist `CODEBASE` sollte die Datei ".ocx" für das ActiveX-Steuerelement und eine INF-Datei zur Steuerung der Installation enthalten. Erstellen Sie die CAB-Datei den Namen der Steuerelementdatei angeben und eine INF-Datei. Verwenden Sie keine abhängigen DLLs, die möglicherweise bereits auf dem System in der CAB-Datei vorhanden. MFC-DLLs werden z. B. in einer separaten CAB-Datei gepackt und von der steuernde INF-Datei bezeichnet.  
  
 Weitere Informationen zum Erstellen einer CAB-Datei finden Sie unter [erstellen eine CAB-Datei](http://msdn.microsoft.com/en-us/cc52fd09-bdf6-4410-a693-149a308f36a3).  
  
### <a name="the-inf-file"></a>Die INF-Datei  
 Das folgende Beispiel, spindial.inf, Listen benötigt die unterstützenden Dateien und die Versionsinformationen für die MFC-Spindial steuern. Beachten Sie, dass der Speicherort für die MFC-DLLs ist eine Microsoft-Website. Die mfc42.cab bereitgestellt und von Microsoft signiert.  
  
```  
Contents of spindial.inf:  
[mfc42installer]   
file-win32-x86=http://activex.microsoft.com/controls/vc/mfc42.cab   
[Olepro32.dll] - FileVersion=5,
    0,
    4261,
    0  
[Mfc42.dll] - FileVersion=6,
    0,
    8168,
    0  
[Msvcrt.dll] - FileVersion=6,
    0,
    8168,
    0  
```  
  
### <a name="the-object-tag"></a>Die \<Objekt >-Tag  
 Im folgende Beispiel wird die Verwendung der `<OBJECT>` -Tag, um das Spindial MFC-Beispiel-Steuerelement zu verpacken.  
  
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
  
 In diesem Fall enthält Beispiel enthält spindial.cab zwei Dateien spindial.ocx und spindial.inf. Der folgende Befehl wird die CAB-Datei erstellen:  
  
```  
C:\CabDevKit\cabarc.exe -s 6144 N spindial.cab spindial.ocx spindial.inf   
```  
  
 Die `-s 6144` Parameter reserviert Speicherplatz in der CAB-Datei zum Signieren von Code.  
  
### <a name="the-version-tag"></a>Das Versionstag  
 Wie Sie sehen, die `#Version` Informationen, die mit einer CAB-Datei angegeben gelten für das Steuerelement, das gemäß der `CLASSID` Parameter von der `<OBJECT>` Tag.  
  
 Abhängig von der Version, die angegeben wird können Sie den Download des Steuerelements erzwingen. Für die vollständige Spezifikation der der `OBJECT` Tag einschließlich der `CODEBASE` Parameter, finden Sie in der W3C-Verweis.  
  
##  <a name="_core_marking_a_control_safe_for_scripting_and_initializing"></a>Markieren ein sicheres Steuerelement für Skripting und Initialisierung  
 ActiveX-Steuerelemente verwendet, die in Webseiten sollte als sicher für Skripting und zum Initialisieren, wenn diese in der Tat sicher sind sichere gekennzeichnet werden. Ein sicheres Steuerelement Datenträger-e/a auszuführen oder direkt Zugriff auf den Arbeitsspeicher oder die Register eines Computers nicht.  
  
 Steuerelemente können als sicher für Skripting und sicher über die Registrierung initialisieren gekennzeichnet werden. Ändern Sie `DllRegisterServer` zum Hinzufügen von Einträgen, die etwa wie folgt auf das Steuerelement als sicher für Skripting und Persistenz in der Registrierung zu markieren. Eine alternative Methode besteht darin implementieren `IObjectSafety`.  
  
 Definieren Sie die GUIDs (Globally Unique Identifier) für das Steuerelement, es sicher für Skripting und für den permanenten Speicher zu kennzeichnen. Steuerelemente, die sicher Skripts erstellt werden können, werden einen Registrierungseintrag ähnlich der folgenden enthalten:  
  
```  
HKEY_CLASSES_ROOT\Component Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}  
```  
  
 Steuerelemente, die sicher aus persistenten Daten initialisiert werden, können sind für den permanenten Speicher mit einem Registrierungseintrag ähnelt sicher gekennzeichnet:  
  
```  
HKEY_CLASSES_ROOT\Component Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}  
```  
  
 Fügen Sie Einträge ähnlich dem folgenden (durch Ersetzen des Steuerelements Klassen-ID anstelle von `{06889605-B8D0-101A-91F1-00608CEAD5B3}`) die folgenden Klassen-ID Ihrer Schlüssel zugeordnet werden soll:  
  
```  
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}   
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}   
```  
  
##  <a name="_core_licensing_issues"></a>Lizenzierungsprobleme  
 Wenn Sie ein lizenziertes Steuerelement auf einer Webseite verwenden möchten, müssen Sie sicherstellen, dass des Lizenzvertrags zu dessen Verwendung im Internet zulässt und eine Lizenz-Paketdatei (LPK) dafür erstellen.  
  
 Ein lizenziertes ActiveX-Steuerelement wird in einer HTML-Seite nicht ordnungsgemäß geladen, wenn der Computer mit Internet Explorer nicht lizenziert ist, um das Steuerelement zu verwenden. Wenn ein lizenziertes Steuerelement mit Visual C++ erstellt wurde, wird die HTML-Seite, die mithilfe des Steuerelements ordnungsgemäß laden Sie z. B. auf dem Computer, auf dem das Steuerelement erstellt wurde, aber es wird nicht auf einem anderen Computer geladen werden, wenn die Lizenzinformationen enthalten ist.  
  
 Um ein lizenziertes ActiveX-Steuerelement in Internet Explorer verwenden zu können, müssen Sie prüfen, stellen Sie sicher, dass die Lizenz für das Steuerelement zugelassen Lizenzvertrag des Herstellers:  
  
-   Neuverteilung  
  
-   Verwenden des Steuerelements im Internet  
  
-   Verwenden des Parameters Codebasis  
  
 Um ein lizenziertes Steuerelement in einer HTML-Seite auf einem Computer Lizenzpaketdatei verwenden zu können, müssen Sie eine Lizenz-Paketdatei (LPK) generieren. Die LPK-Datei enthält die Laufzeit-Lizenzen für lizenzierte Steuerelemente in der HTML-Seite. Diese Datei wird über LPK_TOOL generiert. EXE-Datei mit dem ActiveX-SDK enthalten. Weitere Informationen finden Sie in der MSDN-Website unter [http://msdn.microsoft.com](http://msdn.microsoft.com).  
  
#### <a name="to-create-an-lpk-file"></a>So erstellen Sie eine LPK-Datei  
  
1.  Führen Sie LPK_TOOL. EXE-Datei auf einem Computer, der lizenziert ist, um das Steuerelement zu verwenden.  
  
2.  In der **License Package Authoring Tool** Dialogfeld die **verfügbaren Steuerelemente** Listenfeld, wählen Sie die einzelnen lizenzierten ActiveX-Steuerelement, das auf der Seite "HTML" verwendet werden, und klicken Sie auf **hinzufügen**.  
  
3.  Klicken Sie auf **speichern und beenden** und geben Sie einen Namen für die LPK-Datei. Dies erstellt die LPK-Datei und schließen Sie die Anwendung.  
  
#### <a name="to-embed-a-licensed-control-on-an-html-page"></a>So betten Sie ein lizenziertes Steuerelement auf einer HTML-Seite ein.  
  
1.  Bearbeiten Sie die HTML-Seite. Fügen Sie in der HTML-Seite ein \<Objekt >-Tag für das License Manager-Objekt vor allen anderen \<Objekt > RFID-Transponder. Der Lizenz-Manager ist ein ActiveX-Steuerelement, das mit Internet Explorer installiert ist. Die Klassen-ID ist unten dargestellt. Legen Sie die LPKPath-Eigenschaft des License Manager-Objekts, um den Pfad und Namen der LPK-Datei. Sie können nur eine LPK-Datei pro HTML-Seite verwenden.  
  
 ```  
 <OBJECT CLASSID = "clsid:5220cb21-c88d-11cf-b347-00aa00a28331">  
 <PARAM NAME="LPKPath" VALUE="relative URL to .LPK file">  
 </OBJECT>  
 ```  
  
2.  Fügen Sie der \<Objekt >-Tag für das lizenzierte Steuerelement hinter das License Manager-Tag.  
  
     Beispielsweise wird eine HTML-Seite, die das Microsoft MaskedEdit-Steuerelement zeigt unten dargestellt. Die erste Klasse, die für das License Manager-Steuerelement-ID ist, die zweite Klasse, die für das MaskedEdit-Steuerelement-ID ist. Ändern Sie die Tags aus, um auf den relativen Pfad der Datei .lpk verweisen, die Sie zuvor erstellt haben, und fügen Sie ein Objekttag, einschließlich der Klassen-ID für das Steuerelement.  
  
3.  Legen Sie die \<EINBETTEN >-Attribut für die LPK-Datei, wenn das NCompass ActiveX-Plug-in verwenden.  
  
     Wenn das Steuerelement kann, auf anderen angezeigt werden aktiviert aktiv Browsern – z. B. das NCompass ActiveX-Plug-in mit Netscape – müssen Sie hinzufügen die \<EINBETTEN > Syntax wie unten dargestellt.  
  
 ```  
 <OBJECT CLASSID="clsid:5220cb21-c88d-11cf-b347-00aa00a28331">  
 <PARAM NAME="LPKPath" VALUE="maskedit.lpk">  
 
 <EMBED SRC = "maskedit.LPK">  
 
 </OBJECT>  
 <OBJECT CLASSID="clsid:C932BA85-4374-101B-A56C-00AA003668DC" WIDTH=100 HEIGHT=25>  
 </OBJECT>  
 ```  
  
 Weitere Informationen zur Lizenzierung finden Sie unter [ActiveX-Steuerelemente: Lizenzieren eines ActiveX-Steuerelements](../mfc/mfc-activex-controls-licensing-an-activex-control.md).  
  
##  <a name="_core_signing_code"></a>Signieren von Code  
 Signieren von Code dient zum Identifizieren der Quelle des Codes, und um sicherzustellen, dass der Code nicht, seit es geändert hat signiert wurde. Abhängig von den Browsereinstellungen für Sicherheit können Benutzer gewarnt werden, bevor der Code heruntergeladen wird. Benutzer möchten vertrauen Besitzer bestimmter Zertifikate oder Unternehmen, in denen Groß-/Kleinschreibung über eine Codesignatur von Entwicklern vertraut ohne Warnung heruntergeladen werden sollen. Code wird digital signiert, um Manipulationen zu verhindern.  
  
 Stellen Sie sicher, dass der endgültige Code, damit das Steuerelement automatisch heruntergeladen werden kann, ohne Vertrauensstellung Warnmeldungen angemeldet ist. Weitere Informationen zum Signieren von Code, die auf Authenticode im ActiveX-SDK-Dokumentation und überprüfen Sie, [Signieren einer CAB-Datei](http://msdn.microsoft.com/en-us/04d8b47a-8f1c-4b54-ab90-730fcdc03747).  
  
 Je nach Browser und Vertrauenswürdigkeit Sicherheitsstufen möglicherweise ein Zertifikat zum Identifizieren der signierenden Person oder Firma angezeigt. Ist die Sicherheitsstufe auf none festgelegt, oder wenn das signierte Steuerelement Zertifikatsbesitzers vertrauenswürdig ist, wird ein Zertifikat nicht angezeigt werden. Finden Sie unter [Sicherheitsstufen für Internet Explorer-Browser und Verhalten des Steuerelements](#_core_internet_explorer_browser_safety_levels_and_control_behavior) ausführliche Informationen wie die Browser Safety-Einstellung bestimmt, ob das Steuerelement heruntergeladen wird und ein Zertifikat angezeigt.  
  
 Digitale Signatur Garantien Code wurde nicht geändert werden, nach der Signierung worden ist. Ein Hash der wird übernommen und in das Zertifikat eingebettet. Dieser Hash wird später mit einem Hash der nach dem Herunterladen des Codes jedoch vor der Ausführung verglichen. Unternehmen wie Verisign können privaten und öffentlichen Schlüssel zum Signieren von Code erforderlich angeben. Das ActiveX-SDK geliefert wird mit MakeCert ein Hilfsprogramm zum Erstellen von Testzertifikaten.  
  
##  <a name="_core_managing_the_palette"></a>Verwalten der Palette  
 Container bestimmen die Palette und als eine ambient-Eigenschaft verfügbar machen, **DISPID_AMBIENT_PALETTE**. Ein Container (z. B. Internet Explorer) Wählt eine Palette, die durch alle ActiveX-Steuerelemente auf einer Seite verwendet wird, um ihre eigenen Palette zu bestimmen. Dies verhindert die Anzeige Flimmern und stellt ein einheitliches Erscheinungsbild.  
  
 Ein Steuerelement kann überschreiben `OnAmbientPropertyChange` Benachrichtigung über Änderungen an der Palette zu behandeln.  
  
 Ein Steuerelement kann überschreiben `OnGetColorSet` zurückzugebenden eine Farbe auf die Palette zu zeichnen. Container anhand des Rückgabewerts um zu bestimmen, ob ein Steuerelement Palette-fähig ist.  
  
 Ein Steuerelement muss immer ihre Palette im Hintergrund realisiert, unter OCX-96-Richtlinien.  
  
 Ältere Container, die die Palette der ambient-Eigenschaft nicht verwenden sendet `WM_QUERYNEWPALETTE` und `WM_PALETTECHANGED` Nachrichten. Ein Steuerelement kann überschreiben `OnQueryNewPalette` und `OnPaletteChanged` diese Nachrichten zu verarbeiten.  
  
##  <a name="_core_internet_explorer_browser_safety_levels_and_control_behavior"></a>Internet Explorer-Browser-Sicherheitsstufen und Verhalten des Steuerelements  
 Optionen für die Sicherheitsstufe, die vom Benutzer konfigurierbar über einen Browser verfügt. Da Webseiten aktiven Inhalte enthalten kann, der dem Computer eines Benutzers beschädigen kann, können Browser den Benutzer zur Auswahl von Optionen für die Sicherheitsstufe für. Abhängig von der Anzeigemethode ein Browser Sicherheitsstufen implementiert, ein Steuerelement gar nicht heruntergeladen werden kann, oder zeigt ein Zertifikat oder eine Warnmeldung angezeigt, damit der Benutzer zur Laufzeit, ob das Steuerelement heruntergeladen wird oder nicht auswählen kann. Das Verhalten des ActiveX-Steuerelemente unter hoher, mittlerer und geringer Sicherheitsstufen in Internet Explorer ist unten aufgeführt.  
  
### <a name="high-safety-mode"></a>Modus für hohe Sicherheit  
  
-   Unsignierte Steuerelemente werden nicht heruntergeladen werden.  
  
-   Signierte Steuerelemente werden ein Zertifikat angezeigt, wenn nicht vertrauenswürdige (ein Benutzer kann eine Option aus, um den Code aus diesem Zertifikatsbesitzers von nun an immer zu vertrauen auswählen).  
  
-   Nur die Steuerelemente, die als sicher gekennzeichnet werden persistente Daten haben und/oder skriptfähige sein.  
  
### <a name="medium-safety-mode"></a>Mittlere Sicherheitsmodus  
  
-   Unsignierte Steuerelemente zeigt eine Warnung vor dem herunterladen.  
  
-   Signierte Steuerelemente werden ein Zertifikat angezeigt, wenn als nicht vertrauenswürdig eingestuft.  
  
-   Steuerelemente, die nicht als sicher gekennzeichnet werden eine Warnung angezeigt.  
  
### <a name="low-safety-mode"></a>Modus mit niedriger Sicherheit  
  
-   Steuerelemente werden ohne Warnung heruntergeladen.  
  
-   Skripterstellung und Persistenz werden ohne Warnung auftreten.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)   
 [MFC-Internetprogrammiergrundlagen](../mfc/mfc-internet-programming-basics.md)   
 [MFC-ActiveX-Steuerelemente: Lizenzieren eines ActiveX-Steuerelements](../mfc/mfc-activex-controls-licensing-an-activex-control.md)


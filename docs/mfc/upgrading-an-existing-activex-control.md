---
title: Upgrading eines vorhandenen ActiveX-Steuerelements | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dc5bca0f7ff1b2fdb2650eadbcdca4778d9b53ef
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890359"
---
# <a name="upgrading-an-existing-activex-control"></a>Upgrading eines vorhandenen ActiveX-Steuerelements

Vorhandene ActiveX-Steuerelemente (früher OLE-Steuerelemente) kann über das Internet ohne Änderung verwendet werden. Allerdings sollten Sie so ändern Sie die Steuerelemente, um die Leistung zu verbessern.

> [!IMPORTANT]
> ActiveX ist eine veraltete Technologie, die nicht für Neuentwicklungen verwendet werden soll. Weitere Informationen über moderne Technologien, die ActiveX Ersetzen eines finden Sie unter [ActiveX-Steuerelemente](activex-controls.md).

Wenn Sie das Steuerelement auf einer Webseite verwenden, gibt es weitere Überlegungen. Die OCX-Datei und alle zugehörigen Dateien müssen auf dem Zielcomputer oder über das Internet heruntergeladen werden. Dadurch wird die Codegröße als auch herunterladen, die Zeit eines wichtigen Aspekt. Downloads können in einer signierten CAB-Datei verpackt werden. Sie können das Steuerelement als sicher für Skripting und als sicher für die Initialisierung kennzeichnen.

In diesem Artikel werden die folgenden Themen behandelt:

- [Verpacken von Code zum Herunterladen](#_core_packaging_code_for_downloading)

- [Markieren ein Steuerelement sicher für Skripting und Initialisierung](#_core_marking_a_control_safe_for_scripting_and_initializing)

- [Lizenzierungsprobleme](#_core_licensing_issues)

- [Signieren von Code](#_core_signing_code)

- [Verwalten der Palette](#_core_managing_the_palette)

- [Internet Explorer-Browser-Sicherheitsstufen und Verhalten des Steuerelements](#_core_internet_explorer_browser_safety_levels_and_control_behavior)

Sie können auch Optimierungen, hinzufügen, wie in beschrieben [ActiveX-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md). Moniker können verwendet werden, um die Eigenschaften herunterzuladen und große BLOBs asynchron, siehe [ActiveX-Steuerelemente für das Internet](../mfc/activex-controls-on-the-internet.md).

##  <a name="_core_packaging_code_for_downloading"></a> Verpacken von Code zum Herunterladen

Weitere Informationen zu diesem Thema finden Sie unter [Paketerstellung ActiveX-Steuerelemente](https://docs.microsoft.com//previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa751974%28v%3dvs.85%29).

### <a name="the-codebase-tag"></a>Die CODEBASE-Tags

ActiveX-Steuerelemente in Webseiten mit eingebettet sind die `<OBJECT>` Tag. Die `CODEBASE` Parameter, der die `<OBJECT>` -Tag gibt den Speicherort, von dem das Steuerelement heruntergeladen. `CODEBASE` können erfolgreich eine Reihe von verschiedenen Dateitypen zeigen.

### <a name="using-the-codebase-tag-with-an-ocx-file"></a>Verwenden das Tag CODEBASIS mit eine OCX-Datei

```
CODEBASE="http://example.microsoft.com/mycontrol.ocx#version=4,
    70,
    0,
    1086"
```

Diese Lösung nur des Steuerelements OCX-Datei heruntergeladen und alle unterstützenden DLLs, die bereits auf dem Clientcomputer installiert sein muss. Dies funktioniert für Internet Explorer und MFC-ActiveX-Steuerelemente, die mit Visual C++ erstellter, da Internet Explorer mit der Hilfs-DLLs für Visual C++-Steuerelemente geliefert wird. Wenn einem anderen Internetbrowser, die ActiveX-Steuerelement-fähig ist zum Anzeigen der Steuerelemente verwendet wird, funktioniert diese Lösung nicht.

### <a name="using-the-codebase-tag-with-an-inf-file"></a>Verwenden die CODEBASE-Tags mit einer INF-Datei

```
CODEBASE="http://example.microsoft.com/trustme.inf"
```

Eine INF-Datei wird die Installation von einer OCX-Datei und die unterstützenden Dateien zu steuern. Diese Methode wird nicht empfohlen, da es nicht möglich, sich eine INF-Datei ist (finden Sie unter [Code signieren](#_core_signing_code) für Zeiger auf das Signieren von Code).

### <a name="using-the-codebase-tag-with-a-cab-file"></a>Verwenden das Tag CODEBASIS mit einer CAB-Datei

```
CODEBASE="http://example.microsoft.com/acontrol.cab#version=1,
    2,
    0,
    0"
```

CAB-Dateien sind die empfohlene Methode zum Packen von ActiveX-Steuerelementen, die MFC verwenden. Ein MFC-ActiveX-Steuerelement in einer CAB-Datei packen kann eine INF-Datei mit der die Installation von ActiveX-Steuerelement und alle abhängigen DLLs (z. B. die MFC-DLLs) eingeschlossen werden sollen. Verwenden eine CAB-Datei automatisch komprimiert den Code schneller herunterladen. Wenn Sie eine CAB-Datei zum Herunterladen der Komponente verwenden, ist es schneller, zum Signieren der gesamten CAB-Datei anstelle der einzelnen Komponenten.

### <a name="creating-cab-files"></a>Erstellen von CAB-Dateien

Tools zum Erstellen von CAB-Dateien sind nun Bestandteil der [Windows 10 SDK](https://dev.windows.com/downloads/windows-10-sdk).

Die CAB-Datei verweist `CODEBASE` OCX-Datei für das ActiveX-Steuerelement und eine INF-Datei zur Steuerung der Installation enthalten. Erstellen Sie die CAB-Datei den Namen der Steuerelementdatei angeben und eine INF-Datei. Fügen Sie keine abhängigen DLLs, die möglicherweise bereits auf dem System in der CAB-Datei vorhanden sind. MFC-DLLs sind z. B. in einer separaten CAB-Datei verpackt und auf die steuernde INF-Datei verweist.

Weitere Informationen darüber, wie Sie eine CAB-Datei zu erstellen, finden Sie unter [erstellen eine CAB-Datei](/windows/desktop/devnotes/cabinet-api-functions).

### <a name="the-inf-file"></a>Die INF-Datei

Das folgende Beispiel, spindial.inf, Listen benötigt die unterstützenden Dateien und die Versionsinformationen für die MFC-Spindial steuern. Beachten Sie, dass der Speicherort für die MFC-DLLs ist eine Microsoft-Website. Die mfc42.cab ist bereitgestellt und von Microsoft signiert.

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

### <a name="the-object-tag"></a>Die \<OBJECT >-Tag

Das folgende Beispiel veranschaulicht die Verwendung der `<OBJECT>` Tag, das die MFC-Spindial Beispielsteuerelement.

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

In diesem Fall enthält Beispiel enthält spindial.cab spindial.ocx und spindial.inf zwei Dateien. Der folgende Befehl wird die CAB-Datei erstellen:

```
C:\CabDevKit\cabarc.exe -s 6144 N spindial.cab spindial.ocx spindial.inf
```

Die `-s 6144` Parameter reserviert Speicherplatz im CAB-Datei zum Signieren von Code.

### <a name="the-version-tag"></a>Das Versionstag

Beachten Sie hier, dass die `#Version` Informationen, die mit einer CAB-Datei angegeben gelten für das Steuerelement, das gemäß der *CLASSID* Parameter, der die `<OBJECT>` Tag.

Abhängig von der Version angegeben ist können Sie den Download des Steuerelements erzwingen. Für vollständige Spezifikation der der `OBJECT` Tag einschließlich der *CODEBASIS* -Parameter, finden Sie unter der W3C-Verweis.

##  <a name="_core_marking_a_control_safe_for_scripting_and_initializing"></a> Markieren ein Steuerelement sicher für Skripting und Initialisierung

ActiveX-Steuerelemente, die in Webseiten verwendet, sollte als sicher für Skripting und zum Initialisieren, wenn sie in der Tat sicher sind sichere markiert werden. Ein sicheres Steuerelement führen Sie die Datenträger-e/a nicht oder auf den Speicher oder Register eines Computers direkt zugreifen.

Steuerelemente können als sicher für Skripting und sicher über die Registrierung zu initialisieren gekennzeichnet werden. Ändern Sie `DllRegisterServer` zum Hinzufügen von Einträgen, die etwa wie folgt auf das Steuerelement als sicher für Skripting und Persistenz in der Registrierung markieren. Eine alternative Methode ist, implementieren `IObjectSafety`.

Definieren Sie GUIDs (Globally Unique Identifiers) für das Steuerelement, es sicher für Skripting und für die Persistenz zu kennzeichnen. Steuerelemente, die sicher Skripts erstellt werden können, enthält einen Registrierungseintrag, der etwa wie folgt:

```
HKEY_CLASSES_ROOT\Component Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}
```

Steuerelemente, die problemlos von persistenten Daten initialisiert werden können, werden für Persistenz mit einen Registrierungseintrag, der ähnlich wie sicher markiert:

```
HKEY_CLASSES_ROOT\Component Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}
```

Fügen Sie Einträge, die etwa wie folgt (Ersetzen Ihres Steuerelements Klassen-ID anstelle von `{06889605-B8D0-101A-91F1-00608CEAD5B3}`) die folgenden Klassen-ID Ihrer Schlüssel zugeordnet werden soll:

```
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}
```

##  <a name="_core_licensing_issues"></a> Lizenzierungsprobleme

Wenn Sie ein lizenziertes Steuerelement auf einer Webseite verwenden möchten, müssen Sie sicherstellen, dass die Lizenzbedingungen ermöglicht die Verwendung im Internet und eine Lizenz-Paketdatei (LPK) dafür erstellen.

Ein lizenziertes ActiveX-Steuerelement wird in einer HTML-Seite nicht ordnungsgemäß geladen, wenn der Computer mit Internet Explorer zur Verwendung des Steuerelements nicht lizenziert ist. Z. B. wenn ein lizenziertes Steuerelement mit Visual C++ erstellt wurde, wird die HTML-Seite, die mit dem Steuerelement ordnungsgemäß Laden auf dem Computer, in dem das Steuerelement erstellt wurde, aber es wird nicht auf einem anderen Computer geladen, es sei denn, die Informationen zur Lizenzierung enthalten ist.

Um ein lizenziertes ActiveX-Steuerelement in Internet Explorer verwenden zu können, müssen Sie überprüfen, des Anbieters-Software-Lizenzbedingungen zu überprüfen, ob die Lizenz für das Steuerelement lässt:

- Neuverteilung

- Verwenden des Steuerelements auf das Internet

- Verwendung des Parameters Codebasis

Um ein lizenziertes Steuerelement in einer HTML-Seite auf einem Computer Lizenzpaketdatei verwenden zu können, müssen Sie eine Lizenz-Paketdatei (LPK) generieren. Die LPK-Datei enthält die Laufzeit-Lizenzen für lizenzierte Steuerelemente im HTML-Seite. Diese Datei wird mit Hilfe von LPK_TOOL generiert. EXE-Datei die mit dem ActiveX-SDK enthalten ist. Weitere Informationen finden Sie unter der MSDN-Website unter [ http://msdn.microsoft.com ](http://msdn.microsoft.com).

#### <a name="to-create-an-lpk-file"></a>So erstellen Sie eine Datei LPK

1. Führen Sie LPK_TOOL. EXE-Datei auf einem Computer, der zur Verwendung des Steuerelements lizenziert ist.

1. In der **License Package Authoring Tool** Dialogfeld die **verfügbaren Steuerelemente** Listenfeld, wählen Sie die einzelnen lizenzierten ActiveX-Steuerelement, die auf der HTML-Seite verwendet werden, und klicken Sie auf **hinzufügen**.

1. Klicken Sie auf **speichern und beenden Sie** , und geben Sie einen Namen für die LPK-Datei. Dies erstellt die LPK-Datei und schließen Sie die Anwendung.

#### <a name="to-embed-a-licensed-control-on-an-html-page"></a>Um ein lizenziertes Steuerelement auf einer HTML-Seite einzubetten.

1. Bearbeiten Sie Ihre HTML-Seite. Fügen Sie in der HTML-Seite ein \<Objekt >-Tag für das License Manager-Objekt, vor allen anderen \<Objekt > Tags. Die Lizenz-Manager ist ein ActiveX-Steuerelement, das mit Internet Explorer installiert ist. Die Klassen-ID ist unten dargestellt. Legen Sie die LPKPath-Eigenschaft des das License Manager-Objekt, um den Pfad und Namen der LPK-Datei. Sie können nur eine LPK-Datei pro HTML-Seite verwenden.

```
<OBJECT CLASSID = "clsid:5220cb21-c88d-11cf-b347-00aa00a28331">
<PARAM NAME="LPKPath" VALUE="relative URL to .LPK file">
</OBJECT>
```

1. Fügen Sie der \<Objekt >-Tag für das lizenzierte Steuerelement nach dem Tag-Lizenz-Manager.

     Beispielsweise ist eine HTML-Seite, die das Microsoft-MaskedEdit-Steuerelement zeigt unten dargestellt. Die erste Klasse, die für das License Manager-Steuerelement-ID ist, die zweite Klasse, die für das MaskedEdit-Steuerelement-ID ist. Ändern Sie die Tags auf den relativen Pfad der Datei .lpk zu verweisen, die Sie zuvor erstellt haben, und fügen Sie ein Objekttag, einschließlich die Klassen-ID für das Steuerelement.

1. Fügen Sie der \<EINBETTEN >-Attribut für die LPK-Datei, wenn das NCompass ActiveX-Plug-in verwenden.

     Wenn das Steuerelement kann, auf anderen angezeigt werden aktiviert aktiv Browser – z. B. das NCompass ActiveX-Plug-in mit Netscape – müssen Sie hinzufügen, die \<EINBETTEN > Syntax wie unten dargestellt.

```
<OBJECT CLASSID="clsid:5220cb21-c88d-11cf-b347-00aa00a28331">
<PARAM NAME="LPKPath" VALUE="maskedit.lpk">

<EMBED SRC = "maskedit.LPK">

</OBJECT>
<OBJECT CLASSID="clsid:C932BA85-4374-101B-A56C-00AA003668DC" WIDTH=100 HEIGHT=25>
</OBJECT>
```

Weitere Informationen zur Lizenzierung finden Sie unter [ActiveX-Steuerelemente: Lizenzieren eines ActiveX-Steuerelements](../mfc/mfc-activex-controls-licensing-an-activex-control.md).

##  <a name="_core_signing_code"></a> Signieren von Code

Signieren von Code dient zum Identifizieren des Quell-Code, und um sicherzustellen, dass der Code nicht, seit es geändert hat signiert wurde. Abhängig von den Browsereinstellungen für Sicherheit können Benutzer gewarnt, bevor der Code heruntergeladen wird. Benutzer die Möglichkeit, vertrauen bestimmte Inhabern oder Unternehmen, in denen Fall eine Codesignatur von den vertrauenswürdigen ohne Warnung heruntergeladen werden. Code wird digital signiert, um Manipulationen zu vermeiden.

Stellen Sie sicher, dass der resultierende Code signiert ist, damit das Steuerelement automatisch heruntergeladen werden kann, ohne Vertrauensstellung Warnmeldungen an. Weitere Informationen zum Signieren von Code finden Sie in der Dokumentation auf das Authenticode im ActiveX-SDK, und finden Sie unter [eine CAB-Datei signieren](/windows/desktop/devnotes/cabinet-api-functions).

Abhängig von der Vertrauensstellung und Browser auf die Sicherheitseinstellungen kann ein Zertifikat angezeigt werden, um die signierende Person oder Firma zu identifizieren. Wenn die Sicherheitsstufe auf None festgelegt ist oder das Vorzeichen des Steuerelements Zertifikatsbesitzers als vertrauenswürdig eingestuft wird, wird ein Zertifikat nicht angezeigt werden. Finden Sie unter [Sicherheitsstufen für Internet Explorer-Browser und Verhalten des Steuerelements](#_core_internet_explorer_browser_safety_levels_and_control_behavior) Einzelheiten, wie der Browser-sicherheitseinstellung bestimmt, ob das Steuerelement heruntergeladen wird und ein Zertifikat angezeigt.

Digitales Signieren von Garantien Code wurde nicht geändert werden, da es signiert wurde, ist. Ein Hash des Codes wird erstellt und im Zertifikat eingebetteten. Dieser Hash wird später noch Mal mit einem Hash des Codes ausgeführt, nachdem der Code heruntergeladen wird, aber vor der Ausführung verglichen. Unternehmen, wie z. B. Verisign können mit privaten und öffentlichen Schlüssel zum Signieren von Code erforderlich sind angeben. Das ActiveX-SDK im Lieferumfang von "MakeCert", ein Hilfsprogramm für die Testzertifikate zu erstellen.

##  <a name="_core_managing_the_palette"></a> Verwalten der Palette

Container, bestimmen die Palette, und macht sie verfügbar ist als ambient-Eigenschaft, **DISPID_AMBIENT_PALETTE**. Ein Container (z. B. Internet Explorer) Wählt aus eine Palette, die durch alle ActiveX-Steuerelemente auf einer Seite verwendet wird, um ihre eigenen Farbpalette zu bestimmen. Dies verhindert flimmernde und stellt ein konsistentes Erscheinungsbild.

Ein Steuerelement kann überschreiben `OnAmbientPropertyChange` , Benachrichtigung über Änderungen an der Palette zu behandeln.

Ein Steuerelement kann überschreiben `OnGetColorSet` zurückzugebenden Farben die Palette zu zeichnen. Container können, dass den Rückgabewert um zu bestimmen, ob ein Steuerelement Palette-fähig ist.

Gemäß den OCX-96-Richtlinien muss ein Steuerelement immer die Palette im Hintergrund zu erkennen.

Ältere Container, die die Palette der ambient-Eigenschaft nicht verwenden, werden WM_QUERYNEWPALETTE und WM_PALETTECHANGED Nachrichten gesendet. Ein Steuerelement kann überschreiben `OnQueryNewPalette` und `OnPaletteChanged` , diese Nachrichten zu verarbeiten.

##  <a name="_core_internet_explorer_browser_safety_levels_and_control_behavior"></a> Internet Explorer-Browser-Sicherheitsstufen und Verhalten des Steuerelements

Optionen für die Sicherheitsstufe, die vom Benutzer konfigurierbar über einen Browser verfügt. Da Webseiten aktiven Inhalte enthalten kann, der möglicherweise den Computer eines Benutzers beschädigt werden kann, können Browser der Benutzer die Auswahl der Optionen für die Sicherheitsstufe auf. Je nachdem, wie ein Browser Sicherheitsstufen implementiert, ein Steuerelement überhaupt nicht heruntergeladen werden kann, oder zeigt ein Zertifikat oder eine Warnmeldung an, die dem Benutzer ermöglichen, die zur Laufzeit angibt, ob das Steuerelement heruntergeladen werden sollen. Das Verhalten des ActiveX-Steuerelemente unter hoher, mittlerer oder niedriger Sicherheitsstufen in Internet Explorer sind unten aufgeführt.

### <a name="high-safety-mode"></a>Modus für hohe Sicherheit

- Nicht signierte Steuerelemente werden nicht heruntergeladen werden.

- Signierte Steuerelemente können ein Zertifikat werden angezeigt, wenn nicht vertrauenswürdige (ein Benutzer kann eine Option aus, um Code aus der Besitzer dieses Zertifikats von nun an immer zu vertrauen auswählen).

- Nur die Steuerelemente, die als sicher gekennzeichnet werden werden skriptfähige und/oder persistente Daten verfügen.

### <a name="medium-safety-mode"></a>Mittlere Sicherheitsstufe

- Nicht signierte Steuerelemente zeigt eine Warnung vor dem herunterladen.

- Wenn als nicht vertrauenswürdig eingestuft werden ein Zertifikat von signierte Steuerelemente angezeigt werden.

- Steuerelemente, die nicht als sicher gekennzeichnet werden eine Warnung angezeigt.

### <a name="low-safety-mode"></a>Im Modus mit niedriger Sicherheit

- Steuerelemente werden ohne Warnung heruntergeladen.

- Skripterstellung und Persistenz werden ohne Warnung auftreten.

## <a name="see-also"></a>Siehe auch

[MFC-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)<br/>
[Grundlagen der MFC-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)<br/>
[MFC-ActiveX-Steuerelemente: Lizenzieren eines ActiveX-Steuerelements](../mfc/mfc-activex-controls-licensing-an-activex-control.md)


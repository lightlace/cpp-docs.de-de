---
title: Upgrading eines vorhandenen ActiveX-Steuerelements
ms.date: 09/12/2018
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
ms.openlocfilehash: 06c39240d3718f6fbaa15b46abeb8ac9132b5945
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510859"
---
# <a name="upgrading-an-existing-activex-control"></a>Upgrading eines vorhandenen ActiveX-Steuerelements

Vorhandene ActiveX-Steuerelemente (früher OLE-Steuerelemente) können ohne Änderung im Internet verwendet werden. Möglicherweise möchten Sie jedoch Steuerelemente ändern, um die Leistung zu verbessern.

> [!IMPORTANT]
> ActiveX ist eine ältere Technologie, die nicht für die neue Entwicklung verwendet werden sollte. Weitere Informationen zu modernen Technologien, die ActiveX ersetzen, finden Sie unter ActiveX-Steuer [Elemente](activex-controls.md).

Wenn Sie das Steuerelement auf einer Webseite verwenden, sind weitere Überlegungen zu beachten. Die OCX-Datei und alle unterstützenden Dateien müssen sich auf dem Zielcomputer befinden oder über das Internet heruntergeladen werden. Dadurch wird die Codegröße und Downloadzeit ein wichtiger Aspekt. Downloads können in einer signierten CAB-Datei verpackt werden. Sie können Ihr Steuerelement als sicher für die Skripterstellung markieren und als sicher für die Initialisierung festlegen.

In diesem Artikel werden die folgenden Themen behandelt:

- [Verpacken von Code zum herunterladen](#_core_packaging_code_for_downloading)

- [Markieren eines Steuer Elements für die Skripterstellung und Initialisierung](#_core_marking_a_control_safe_for_scripting_and_initializing)

- [Lizenzierungsprobleme](#_core_licensing_issues)

- [Signieren von Code](#_core_signing_code)

- [Verwalten der Palette](#_core_managing_the_palette)

- [Internet Explorer-Browser-Sicherheitsebenen und Steuerelement Verhalten](#_core_internet_explorer_browser_safety_levels_and_control_behavior)

Sie können auch Optimierungen hinzufügen, wie unter [ActiveX-Steuerelemente beschrieben: Optimierung](../mfc/mfc-activex-controls-optimization.md). Moniker können verwendet werden, um Eigenschaften und große blobelemente asynchron herunterzuladen, wie in ActiveX-Steuer [Elementen im Internet](../mfc/activex-controls-on-the-internet.md)beschrieben.

##  <a name="_core_packaging_code_for_downloading"></a>Verpacken von Code zum herunterladen

Weitere Informationen zu diesem Betreff finden Sie unter [Packen von ActiveX](https://docs.microsoft.com//previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa751974%28v%3dvs.85%29)-Steuerelementen.

### <a name="the-codebase-tag"></a>Das CodeBase-Tag

ActiveX-Steuerelemente werden mit dem `<OBJECT>` -Tag in Webseiten eingebettet. Der `CODEBASE` -Parameter `<OBJECT>` des-Tags gibt den Speicherort an, von dem das Steuerelement heruntergeladen werden soll. `CODEBASE`kann auf eine Reihe von verschiedenen Dateitypen erfolgreich verweisen.

### <a name="using-the-codebase-tag-with-an-ocx-file"></a>Verwenden des CodeBase-Tags mit einer OCX-Datei

```
CODEBASE="http://example.microsoft.com/mycontrol.ocx#version=4,
    70,
    0,
    1086"
```

Diese Lösung lädt nur die OCX-Datei des Steuer Elements herunter und erfordert, dass alle unterstützenden DLLs bereits auf dem Client Computer installiert sind. Dies funktioniert für Internet Explorer-und MFC-ActiveX-Steuerelemente C++, die mit Visual erstellt werden, da Internet Explorer mit den C++ unterstützenden DLLs für visuelle Steuerelemente ausgeliefert wird. Wenn ein anderer Internet Browser, der ActiveX-Steuerelement fähig ist, zum Anzeigen dieses Steuer Elements verwendet wird, funktioniert diese Lösung nicht.

### <a name="using-the-codebase-tag-with-an-inf-file"></a>Verwenden des CodeBase-Tags mit einer INF-Datei

```
CODEBASE="http://example.microsoft.com/trustme.inf"
```

Eine INF-Datei steuert die Installation von OCX-Dateien und deren unterstützenden Dateien. Diese Methode wird nicht empfohlen, da es nicht möglich ist, eine INF-Datei zu signieren (Weitere Informationen finden Sie [unter Signieren](#_core_signing_code) von Code für Zeiger auf Code Signatur).

### <a name="using-the-codebase-tag-with-a-cab-file"></a>Verwenden des CodeBase-Tags mit einer CAB-Datei

```
CODEBASE="http://example.microsoft.com/acontrol.cab#version=1,
    2,
    0,
    0"
```

CAB-Dateien sind die empfohlene Methode, um ActiveX-Steuerelemente zu verpacken, die MFC verwenden. Beim Verpacken eines MFC-ActiveX-Steuer Elements in einer CAB-Datei kann eine INF-Datei eingeschlossen werden, um die Installation des ActiveX-Steuer Elements und aller abhängigen DLLs (z. b. MFC-DLLs) zu steuern. Wenn Sie eine CAB-Datei verwenden, wird der Code für einen schnelleren Download automatisch komprimiert. Wenn Sie eine CAB-Datei für das Herunterladen von Komponenten verwenden, ist es schneller, die gesamte CAB-Datei zu signieren, als jede einzelne Komponente.

### <a name="creating-cab-files"></a>Erstellen von CAB-Dateien

Tools zum Erstellen von CAB-Dateien sind jetzt Bestandteil des [Windows 10-SDK](https://dev.windows.com/downloads/windows-10-sdk).

Die CAB-Datei, auf `CODEBASE` die von verwiesen wird, sollte die OCX-Datei für das ActiveX-Steuerelement und eine INF-Datei enthalten, um die Installation zu steuern. Sie erstellen die CAB-Datei, indem Sie den Namen der Steuerelement Datei und eine INF-Datei angeben. Fügen Sie keine abhängigen DLLs ein, die möglicherweise bereits auf dem System in dieser CAB-Datei vorhanden sind. Die MFC-DLLs werden z. b. in einer separaten CAB-Datei verpackt, auf die von der steuernden INF-Datei verwiesen wird.

Ausführliche Informationen zum Erstellen einer CAB-Datei finden Sie unter [Erstellen einer CAB-Datei](/windows/win32/devnotes/cabinet-api-functions).

### <a name="the-inf-file"></a>Die INF-Datei

Im folgenden Beispiel, SPINDIAL. inf, werden die unterstützenden Dateien und die Versionsinformationen aufgelistet, die für das MFC-SPINDIAL-Steuerelement benötigt werden. Beachten Sie, dass der Speicherort für die MFC-DLLs eine Microsoft-Website ist. MFC42. cab wird von Microsoft bereitgestellt und signiert.

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

### <a name="the-object-tag"></a>Das \<Objekt >-Tags

Das folgende Beispiel veranschaulicht die Verwendung `<OBJECT>` des-Tags, um das MFC-Beispiel Steuerelement SPINDIAL zu verpacken.

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

In diesem Fall enthält "SPINDIAL. cab" zwei Dateien: "SPINDIAL. ocx" und "SPINDIAL. inf". Mit dem folgenden Befehl wird die CAB-Datei erstellt:

```
C:\CabDevKit\cabarc.exe -s 6144 N spindial.cab spindial.ocx spindial.inf
```

Der `-s 6144` -Parameter reserviert Platz in der CAB-Datei für die Code Signatur.

### <a name="the-version-tag"></a>Das Versionstag

Beachten Sie hier, `#Version` dass die mit einer CAB-Datei angegebenen Informationen für das Steuerelement gelten, das durch den `<OBJECT>` *ClassID-* Parameter des-Tags angegeben wird.

Abhängig von der angegebenen Version können Sie das Herunterladen des Steuer Elements erzwingen. Umfassende Spezifikationen des `OBJECT` Tags einschließlich des *CodeBase* -Parameters finden Sie in der W3C-Referenz.

##  <a name="_core_marking_a_control_safe_for_scripting_and_initializing"></a>Markieren eines Steuer Elements für die Skripterstellung und Initialisierung

ActiveX-Steuerelemente, die auf Webseiten verwendet werden, sollten als sicher für Skripts gekennzeichnet und für die Initialisierung sicher sein, wenn Sie sicher sind. Ein sicheres Steuerelement führt keine Datenträger-e/a-Vorgänge aus oder greift direkt auf den Speicher oder die Register eines Computers zu

Steuerelemente können für die Skripterstellung als sicher gekennzeichnet werden und sind für die Initialisierung über die Registrierung sicher. Ändern `DllRegisterServer` Sie, um Einträge ähnlich der folgenden hinzuzufügen, um das-Steuerelement für die Skripterstellung und Persistenz in der Registrierung zu kennzeichnen. Eine alternative Methode ist die Implementierung `IObjectSafety`von.

Sie definieren GUIDs (Global Unique Identifier) für das Steuerelement, um es für die Skripterstellung und Persistenz sicher zu kennzeichnen. Steuerelemente, für die ein sicheres Skript erstellt werden kann, enthalten einen Registrierungs Eintrag ähnlich dem folgenden:

```
HKEY_CLASSES_ROOT\Component Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}
```

Steuerelemente, die auf sichere Weise von persistenten Daten initialisiert werden können, sind mit einem Registrierungs Eintrag, der etwa wie folgt aussieht, als sicher

```
HKEY_CLASSES_ROOT\Component Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}
```

Fügen Sie Einträge ähnlich der folgenden hinzu (ersetzen Sie die Klassen-ID Ihres Steuer Elements `{06889605-B8D0-101A-91F1-00608CEAD5B3}`anstelle von), um Ihre Schlüssel mit der folgenden Klassen-ID zuzuordnen:

```
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}
```

##  <a name="_core_licensing_issues"></a>Lizenzierungsprobleme

Wenn Sie ein lizenziertes Steuerelement auf einer Webseite verwenden möchten, müssen Sie überprüfen, ob der Lizenzvertrag seine Verwendung im Internet zulässt, und eine Lizenzpaket Datei (LPK) für die Seite erstellen.

Ein lizenziertes ActiveX-Steuerelement wird auf einer HTML-Seite nicht ordnungsgemäß geladen, wenn der Computer mit Internet Explorer nicht für die Verwendung des Steuer Elements lizenziert ist. Wenn z. b. ein lizenziertes Steuerelement mithilfe C++von Visual erstellt wurde, wird die HTML-Seite mit dem Steuerelement auf dem Computer, auf dem das Steuerelement erstellt wurde, ordnungsgemäß geladen, aber nicht auf einem anderen Computer, es sei denn, es sind Lizenzierungsinformationen enthalten

Wenn Sie ein lizenziertes ActiveX-Steuerelement in Internet Explorer verwenden möchten, müssen Sie den Lizenzvertrag des Anbieters prüfen, um zu überprüfen, ob die Lizenz für das Steuerelement zulässig ist

- Neuverteilung

- Verwendung des-Steuer Elements im Internet

- Verwendung des CodeBase-Parameters

Wenn Sie ein lizenziertes Steuerelement in einer HTML-Seite auf einem nicht lizenzierten Computer verwenden möchten, müssen Sie eine Lizenzpaket Datei (LPK) generieren. Die LPK-Datei enthält Laufzeitlizenzen für lizenzierte Steuerelemente auf der HTML-Seite. Diese Datei wird über LPK_TOOL generiert. EXE, das mit dem ActiveX SDK ausgestattet ist.

#### <a name="to-create-an-lpk-file"></a>So erstellen Sie eine LPK-Datei

1. Führen Sie LPK_TOOL aus. EXE auf einem Computer, der für die Verwendung des Steuer Elements lizenziert ist.

1. Wählen Sie im Dialogfeld **Lizenzpaket** Erstellungs Tool im Listenfeld **Verfügbare Steuerelemente** jedes lizenzierte ActiveX-Steuerelement aus, das auf der HTML-Seite verwendet werden soll, und klicken Sie auf **Hinzufügen**.

1. Klicken Sie auf **Save & Exit** , und geben Sie einen Namen für die LPK-Datei ein. Dadurch wird die LPK-Datei erstellt und die Anwendung geschlossen.

#### <a name="to-embed-a-licensed-control-on-an-html-page"></a>So Betten Sie ein lizenziertes Steuerelement auf einer HTML-Seite ein

1. Bearbeiten Sie die HTML-Seite. Fügen Sie auf der Seite HTML vor \<allen anderen \<Objekten > Tags ein Objekt >-Tag für das Lizenz-Manager-Objekt ein. Der Lizenz-Manager ist ein ActiveX-Steuerelement, das mit Internet Explorer installiert wird. Die Klassen-ID ist unten dargestellt. Legen Sie die LPKPath-Eigenschaft des License Manager-Objekts auf den Pfad und den Namen der LPK-Datei fest. Pro HTML-Seite kann nur eine LPK-Datei vorhanden sein.

```
<OBJECT CLASSID = "clsid:5220cb21-c88d-11cf-b347-00aa00a28331">
<PARAM NAME="LPKPath" VALUE="relative URL to .LPK file">
</OBJECT>
```

1. Fügen Sie \<das Objekt > Tag für Ihr lizenziertes Steuerelement nach dem Lizenz-Manager-Tag ein.

   Beispielsweise wird eine HTML-Seite angezeigt, auf der das von Microsoft maskierte Bearbeitungs Steuerelement angezeigt wird. Die erste Klassen-ID ist für das License Manager-Steuerelement, die zweite Klassen-ID ist für das maskierte Bearbeitungs Steuerelement. Ändern Sie die Tags so, dass Sie auf den relativen Pfad der LPK-Datei verweisen, die Sie zuvor erstellt haben, und fügen Sie ein Objekttag einschließlich der Klassen-ID für das Steuerelement hinzu.

1. Fügen Sie \<das Einbettungs > Attribut für die LPK-Datei ein, wenn Sie das NCompass-ActiveX-Plug-in verwenden.

   Wenn das Steuerelement möglicherweise in anderen aktiv aktivierten Browsern angezeigt wird – z. b. Netscape, das das NCompass-ActiveX-Plug \<-in verwendet – müssen Sie wie unten gezeigt die Syntax Einbettungs > hinzufügen.

```
<OBJECT CLASSID="clsid:5220cb21-c88d-11cf-b347-00aa00a28331">
<PARAM NAME="LPKPath" VALUE="maskedit.lpk">

<EMBED SRC = "maskedit.LPK">

</OBJECT>
<OBJECT CLASSID="clsid:C932BA85-4374-101B-A56C-00AA003668DC" WIDTH=100 HEIGHT=25>
</OBJECT>
```

Weitere Informationen zur Steuerelement Lizenzierung finden [Sie unter ActiveX-Steuerelemente: Lizenzieren eines ActiveX](../mfc/mfc-activex-controls-licensing-an-activex-control.md)-Steuer Elements.

##  <a name="_core_signing_code"></a>Signieren von Code

Die Code Signatur dient zum Identifizieren der Codequelle und zum sicherstellen, dass der Code seit der Signierung nicht geändert wurde. Abhängig von den Sicherheitseinstellungen des Browsers werden Benutzer möglicherweise gewarnt, bevor der Code heruntergeladen wird. Benutzer können bestimmten Zertifikat Besitzern oder-Unternehmen vertrauen. in diesem Fall wird der von diesen vertrauenswürdigen Code signierte Code ohne Warnung heruntergeladen. Code wird digital signiert, um Manipulationen zu vermeiden.

Stellen Sie sicher, dass der endgültige Code signiert ist, damit das Steuerelement automatisch heruntergeladen werden kann, ohne dass Warnmeldungen angezeigt werden. Ausführliche Informationen zum Signieren von Code finden Sie in der Dokumentation zu Authenticode im ActiveX SDK und [unter Signieren einer CAB-Datei](/windows/win32/devnotes/cabinet-api-functions).

Abhängig von den Einstellungen der Vertrauensstellungs-und Browser Sicherheit wird möglicherweise ein Zertifikat angezeigt, um die Signatur Person oder das Unternehmen zu identifizieren. Wenn die Sicherheitsstufe "None" ist oder wenn der Besitzer des Zertifikats des signierten Steuer Elements vertrauenswürdig ist, wird kein Zertifikat angezeigt. Ausführliche Informationen dazu, wie die Browser-Sicherheitseinstellung bestimmt, ob Ihr Steuerelement heruntergeladen und ein Zertifikat angezeigt wird, finden Sie unter [Internet Explorer-Browser Sicherheitsebenen und Steuerungs Verhalten](#_core_internet_explorer_browser_safety_levels_and_control_behavior) .

Der Code für die digitale Signierung wurde nicht geändert, da er signiert wurde. Ein Hashwert des Codes wird übernommen und in das Zertifikat eingebettet. Dieser Hash wird zu einem späteren Zeitpunkt mit einem Hashwert des Codes verglichen, der nach dem Herunterladen des Codes, aber vor der Ausführung ausgeführt wird. Unternehmen wie VeriSign können private und öffentliche Schlüssel bereitstellen, die zum Signieren von Code erforderlich sind. Das ActiveX SDK wird mit Makecert ausgeliefert, einem Hilfsprogramm zum Erstellen von Test Zertifikaten.

##  <a name="_core_managing_the_palette"></a>Verwalten der Palette

Container bestimmen die Palette und stellen Sie als Ambient-Eigenschaft ( **DISPID_AMBIENT_PALETTE**) zur Verfügung. Ein Container (z. b. Internet Explorer) wählt eine Palette aus, die von allen ActiveX-Steuerelementen auf einer Seite verwendet wird, um Ihre eigene Palette zu bestimmen. Dies verhindert das Anzeigen von Flimmern und stellt eine konsistente Darstellung dar.

Ein Steuerelement kann `OnAmbientPropertyChange` überschreiben, um Benachrichtigungen über Änderungen an der Palette zu verarbeiten.

Ein Steuerelement kann `OnGetColorSet` überschreiben, um eine Farbmenge zum Zeichnen der Palette zurückzugeben. Container verwenden den Rückgabewert, um zu bestimmen, ob ein Steuerelement palettenfähig ist.

Unter ocx 96-Richtlinien muss ein Steuerelement immer seine Palette im Hintergrund erkennen.

Ältere Container, die die Ambient-Palette-Eigenschaft nicht verwenden, senden WM_QUERYNEWPALETTE-und WM_PALETTECHANGED-Nachrichten. Ein Steuerelement kann `OnQueryNewPalette` diese `OnPaletteChanged` Nachrichten überschreiben und verarbeiten.

##  <a name="_core_internet_explorer_browser_safety_levels_and_control_behavior"></a>Internet Explorer-Browser-Sicherheitsebenen und Steuerelement Verhalten

Ein Browser verfügt über Optionen für die Sicherheitsstufe, die vom Benutzer konfiguriert werden können. Da Webseiten aktive Inhalte enthalten können, die möglicherweise den Computer eines Benutzers beschädigen, ermöglichen Browser dem Benutzer die Auswahl von Optionen für die Sicherheitsstufe. Abhängig von der Art und Weise, in der ein Browser Sicherheitsebenen implementiert, kann ein Steuerelement überhaupt nicht heruntergeladen werden, oder es wird ein Zertifikat oder eine Warnmeldung angezeigt, mit der der Benutzer zur Laufzeit auswählen kann, ob das Steuerelement heruntergeladen werden soll. Das Verhalten von ActiveX-Steuerelementen unter hoch-, Mittel-und niedriger Sicherheitsstufe in Internet Explorer ist unten aufgeführt.

### <a name="high-safety-mode"></a>Modus für hohe Sicherheit

- Nicht signierte Steuerelemente werden nicht heruntergeladen.

- Signierte Steuerelemente zeigen ein Zertifikat an, wenn es nicht vertrauenswürdig ist (ein Benutzer kann eine Option auswählen, um Code von diesem Zertifikat Besitzer immer zu Vertrauen).

- Nur Steuerelemente, die als sicher gekennzeichnet sind, haben persistente Daten und/oder sind skriptfähig.

### <a name="medium-safety-mode"></a>Mittlerer Sicherheitsmodus

- Bei nicht signierten Steuerelementen wird vor dem herunterladen eine Warnung angezeigt.

- Signierte Steuerelemente zeigen ein Zertifikat an, wenn nicht vertrauenswürdig.

- Steuerelemente, die nicht als sicher gekennzeichnet sind, zeigen eine Warnung an.

### <a name="low-safety-mode"></a>Modus mit niedriger Sicherheit

- Steuerelemente werden ohne Warnung heruntergeladen.

- Skripterstellung und Persistenz treten ohne Warnung auf.

## <a name="see-also"></a>Siehe auch

[MFC-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)<br/>
[Grundlagen der MFC-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)<br/>
[MFC-ActiveX-Steuerelemente: Lizenzieren eines ActiveX-Steuerelements](../mfc/mfc-activex-controls-licensing-an-activex-control.md)

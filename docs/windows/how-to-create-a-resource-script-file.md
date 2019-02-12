---
title: 'Vorgehensweise: Erstellen von Ressourcen (C++)'
ms.date: 11/04/2016
f1_keywords:
- vc.editors.resource
- vc.resvw.add.MFC
- vs.resourceview.F1
- vc.editors.insertresource
- vc.editors.newcustomresource
helpviewer_keywords:
- rc files [C++], creating
- .rc files [C++], creating
- resource script files [C++], creating
- resources [C++], viewing
- rc files [C++], viewing resources
- .rc files [C++], viewing resources
- resource script files [C++], viewing resources
- resource script files [C++], opening in text format
- .rc files [C++], opening in text format
- rc files [C++], opening in text format
- rc files [C++], adding MFC support
- .rc files [C++], adding MFC support
- MFC, adding support to resource scripts files
- resource script files [C++], adding MFC support
- toolbars [C++], resources
- resource toolbars
- resources [C++], creating
- Resource View window
- resources [C++], adding
- Add Resource dialog box [C++]
- Custom Resource Type dialog box [C++]
- language-specific template files [C++]
- resource templates
- rct files [C++]
- templates, resource templates
- resources [C++], templates
- .rct files [C++]
ms.assetid: 82be732a-cdcd-4a58-8de7-976d1418f86b
ms.openlocfilehash: 5a0bc6370d0973d63eb16ac992251531aa2e5193
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56152390"
---
# <a name="how-to-create-resources-c"></a>Vorgehensweise: Erstellen von Ressourcen (C++)

> [!NOTE]
> Die **Ressourcen-Editor-** oder **Ressourcenansicht** ist in Express-Editionen nicht verfügbar.
>
> Diese Informationen nicht auf Ressourcen in Windows-desktop-Anwendungen oder universelle Windows-Plattform-apps gelten. Projekte in .NET-Sprachen verwenden keine Ressourcenskriptdateien. Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcendateien](../windows/resource-files-visual-studio.md), [App-Ressourcen und das ressourcenverwaltungssystem](/windows/uwp/app-resources/), und [Ressourcen in desktop-apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*.

## <a name="create-a-resource-script"></a>Erstellen Sie ein Ressourcenskript

Bevor Sie zu erstellen und Ihrem Projekt neue Ressourcen hinzufügen, müssen Sie zuerst eine Ressourcenskriptdatei (.rc) erstellen.

> [!NOTE]
> Eine Ressourcenskriptdatei (.rc) kann nur in ein vorhandenes Projekt aufgenommen werden, das bereits in der Visual Studio-IDE geladen wurde. Sie können kein eigenständiges Ressourcenskript (außerhalb des Projekts) erstellen. Ressourcenvorlagen (RCT-Dateien) können jederzeit erstellt werden.

### <a name="to-create-a-resource-script"></a>Erstellen Sie ein Ressourcenskript

1. Setzen Sie den Fokus auf den vorhandenen Projektordner in **Projektmappen-Explorer**, z. B. *"meinProjekt"*.

   > [!NOTE]
   > Verwechseln Sie nicht mit dem Projektmappenordner im Projektordner **Projektmappen-Explorer**. Wenn Sie den Fokus verschieben, auf die **Lösung** -Ordner, Ihre Auswahl in der **neues Element hinzufügen** Dialogfeld unterscheiden sich.

1. Wählen Sie im Menü **Projekt** die Option **Neues Element hinzufügen** aus.

1. In der **neues Element hinzufügen** wählen Sie im Dialogfeld die **Visual C++** Ordner wählen Sie dann **Ressourcendatei (.rc)** im rechten Bereich.

1. Geben Sie einen Namen für Ihre Ressourcenskript in die **Namen** Text Feld aus, und wählen Sie dann **öffnen**.

### <a name="to-open-a-resource-script"></a>Öffnen Sie ein Ressourcenskript

Sie können Ressourcen in einem Ressourcenskript anzeigen, ohne dass ein Projekt zu öffnen. Die Skriptdatei wird geöffnet, in einem Dokumentfenster geöffnet, anstatt in der **Ressourcenansicht** Fenster (wie dies der Fall ist, wenn die Datei innerhalb eines Projekts geöffnet ist).

> [!NOTE]
> Einige Befehle sind verfügbar, nur, wenn die Datei geöffnet eigenständig (außerhalb eines Projekts) ist. Öffnen eine eigenständige Datei bedeutet, dass es ohne Laden des Projekts zu öffnen.
>
> Um beispielsweise eine Datei in einem anderen Format oder als einen anderen Dateinamen speichern (als die **speichern unter** Befehl ist nicht verfügbar, für die Datei in einem Projekt). Wenn Sie das Projekt zuerst mit öffnen **Datei** > **öffnen** > **Projekt**, diese Befehle sind nicht verfügbar.

So öffnen Sie eine Ressourcenskriptdatei außerhalb eines Projekts:

1. Von der **Datei** , wählen Sie im Menü **öffnen**, wählen Sie dann **Datei**.

1. In der **geöffnete Datei** im Dialogfeld die Ressourcenskriptdatei navigieren, markieren Sie die Datei, und wählen Sie **öffnen**.

Um mehrere Ressourcenskripts außerhalb eines Projekts zu öffnen:

1. Öffnen Sie beide Ressourcendateien eigenständig. Öffnen Sie z. B. *Source1.rc* und *Source2.rc*.

1. Von der **Datei** Menü wählen **öffnen**, und wählen Sie dann **Datei**.

1. In der **Datei öffnen** Dialogfeld navigieren Sie zu den ersten Ressourcenskriptdatei, die Sie öffnen möchten (*Source1.rc*), markieren Sie die Datei, und wählen **öffnen**.

1. Wiederholen Sie den vorherigen Schritt zum Öffnen der zweiten RC-Datei (*Source2.rc*).

   Die RC-Dateien sind nun in separaten Dokumentfenstern geöffnet.

1. Wenn beide RC-Dateien geöffnet sind, in der **Fenster** wählen Sie im Menü (oder mit der rechten Maustaste eine der RC-Dateien) **neue horizontale Registerkartengruppe** oder **neue vertikale Registerkartengruppe**.

   Die Windows werden jetzt nebeneinander angezeigt, damit Sie sie gleichzeitig anzeigen können.

Es gibt viele Situationen, in denen Sie die Inhalte der Ressourcenskriptdatei (.rc) Ihres Projekts anzeigen möchten, ohne dafür eine Ressource wie ein Dialogfeld im entsprechenden Ressourcen-Editor zu öffnen. Beispielsweise möchten Sie möglicherweise nach einer Zeichenfolge über alle Dialogfelder in der Ressourcendatei hinweg suchen, ohne dass Sie dafür jedes einzeln öffnen müssen.

Sie können die Ressourcendatei einfach öffnen, im Text-Format, um alle darin enthaltenen Ressourcen anzuzeigen, und führen globale Vorgänge, die von den Text-Editor unterstützt werden.

> [!NOTE]
> Die Ressourcen-Editoren nicht direkt RC gelesen oder `resource.h` Dateien. Der Ressourcencompiler kompiliert sie in .aps-Dateien, die von den Ressourcen-Editoren genutzt werden. Diese Datei ist ein Kompilierungsschritt und speichert nur symbolische Daten. Wie bei einer normalen Kompilierung werden Informationen, die nicht symbolisch sind (z. B. Kommentare) während der Kompilierung verworfen. Sobald die .aps-Datei mit der RC-Datei nicht mehr synchron, die RC-Datei erneut generiert wird (Wenn Sie speichern, überschreibt der Ressourcen-Editor z. B. die RC-Datei und die `resource.h` Datei). Alle Änderungen an den Ressourcen selbst bleiben in der RC-Datei, aber Kommentare gehen verloren, sobald die .rc-Datei überschrieben wird. Weitere Informationen zur Erhaltung von Kommentaren, finden Sie unter [Einfügen von Ressourcen zur Kompilierungszeit](../windows/how-to-include-resources-at-compile-time.md).

Zu eine Ressourcenskriptdatei im Textformat öffnen:

1. Von der **Datei** Menü die Option **öffnen**, wählen Sie dann **Datei**.

1. In der **geöffnete Datei** Dialogfeld navigieren Sie auf die Ressourcenskriptdatei im Textformat anzeigen möchten.

1. Markieren Sie die Datei, und wählen Sie auf den Dropdown-Pfeil der **öffnen** Schaltfläche (auf der rechten Seite der Schaltfläche).

1. Wählen Sie **Öffnen mit** im Dropdown-Menü.

1. In der **Öffnen mit** wählen Sie im Dialogfeld **Quellcode-Editor (Text)**.

1. Von der **öffnen als** Dropdown-Liste **Text**.

   Die Ressource wird geöffnet, der **Quellcode** Editor.

> [!TIP]
> Eine Verknüpfung mit der rechten Maustaste der in die RC-Datei ist **Projektmappen-Explorer**, wählen Sie **Öffnen mit...**  , und wählen Sie **Quellcode-Editor (Text)**.

### <a name="to-add-mfc-support"></a>MFC-Unterstützung hinzufügen

Normalerweise, wenn Sie eine Microsoft Foundation Class (MFC)-Anwendung für die Verwendung von Windows erstellen die [MFS-Anwendungsassistenten](../mfc/reference/mfc-application-wizard.md), der Assistent generiert eine Reihe grundlegende Dateien (einschließlich einer Ressourcenskriptdatei (.rc)), die Kernfunktionen von enthält die MFC. Jedoch nicht, wenn Sie eine RC-Datei für eine Windows-Anwendung, die nicht auf MFC basiert, zu bearbeiten, folgende MFC-Features verfügbar:

Einige Features, MFC-spezifischen enthalten MFC-Code-Assistenten, menüaufforderungen, Auflisten der Inhalte von Kombinationsfeld-Steuerelemente und ActiveX-Steuerelement hostet.

Um einer Ressourcenskriptdatei MFC-Unterstützung hinzufügen:

1. Öffnen Sie die Ressourcenskriptdatei.

1. In **Ressourcenansicht**, markieren Sie den Ordner "Resources" (z. B. *MFC.rc*).

1. In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window)legen die **MFC Mode** Eigenschaft **"true"**.

   > [!NOTE]
   > Zusätzlich zum Festlegen dieser Eigenschaft, muss die RC-Datei Teil eines MFC-Projekts sein. Z. B. das Festlegen **MFC Mode** zu **"true"** auf eine RC-Datei in einem Win32-Projekt wird nicht bieten Ihnen MFC-Funktionen.

## <a name="create-a-resource"></a>Erstellen einer Ressource

Sie können eine Ressource erstellen, als neue Standardressource (eine Ressource, die nicht in einer Vorlage basiert) oder als eine Ressource, die Vorlage.

Wenn Sie eine neue Ressource erstellen, Visual C++ weist einen eindeutigen Namen, z. B. `IDD_Dialog1`. Sie können diese Ressourcen-ID anpassen, indem Sie die Ressourceneigenschaften entweder im zugehörigen Ressourcen-Editor oder im [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window)bearbeiten.

> [!NOTE]
> Geben Sie kein Ressourcenname oder ID, die von Visual Studio reserviert ist. Reservierten Namen lauten DESIGNINFO, HWB und TEXTINCLUDE, die reservierte ID lautet 255.

Die **Ressourcenansicht** Fenster werden im Projekt enthaltenen Ressourcendateien angezeigt. Erweitern des obersten Ordners (z. B. *Projekt1.rc*) zeigt die Ressourcentypen im, dass die Datei, und erweitern die einzelnen Ressourcentyp zeigt die einzelnen Ressourcen dieses Typs.

> [!TIP]
> Wählen Sie zum Öffnen der Ressourcenansicht (Fenster) **Ressourcenansicht** auf die **Ansicht** Menü (oder verwenden Sie **STRG** + **UMSCHALT**  +  **E**).
>
> Verwendung mit der rechten Maustaste auf die **Ressourcenansicht** Fenster aus, um ein Kontextmenü mit Befehlen starten, oder Doppelklicken auf der Titelleiste, andocken oder Abdocken des Fensters. Mit der rechten Maustaste in der Titelleiste bietet zusätzliche Befehle, die Ihnen ermöglichen, die das Verhalten des Fensters zu steuern. Weitere Informationen finden Sie unter [Windows Management](/visualstudio/ide/customizing-window-layouts-in-visual-studio).

Verwenden der **Ressource hinzufügen** Dialogfeld zum Hinzufügen von Ressourcen zu einem C++-Windows-desktop-Anwendung-Projekt mit den folgenden Eigenschaften:

|Eigenschaft|Beschreibung|
|-|-|
|**Ressourcentyp**|Gibt die Art der zu erstellenden Ressource an.<br/><br/>Der Cursor und die Kategorien der Dialogfeldressourcen können zum Anzeigen zusätzlicher Ressourcen erweitert werden. Diese Ressourcen befinden sich im Visual Studio-...\Microsoft \<Version\>\VC\VCResourceTemplates\\< LCID\>\mfc.rct. Wenn Sie RCT-Dateien hinzufügen, platzieren Sie sie in dieses Verzeichnis auf, oder geben Sie ein anderes [Includepfad](../windows/how-to-specify-include-directories-for-resources.md). Die Ressourcen in diesen Dateien werden dann auf der zweiten Ebene der entsprechenden Kategorie angezeigt. Es ist nicht beschränkt auf die Anzahl von RCT-Dateien, die Sie hinzufügen können.<br/><br/>Die auf der obersten Ebene der Strukturansicht angezeigten Ressourcen sind die von Visual Studio bereitgestellten Standardressourcen.|
|**Neu**|Erstellt eine Ressource, die basierend auf dem Typ, der im ausgewählten der **Ressourcentyp** Feld und die Ressource im geeigneten Editor geöffnet. Beispielsweise wenn Sie eine Ressource erstellen, es öffnet der [Dialog-Editor](../windows/dialog-editor.md).|
|**Importieren**|Öffnet die **importieren** Dialogfeld, in denen Sie können zur Ressource navigieren Sie, in das aktuelle Projekt importiert werden soll. Sie können importieren Bitmap-, Symbol-, Cursor, HTML, sound (. WAV), oder benutzerdefinierte Ressourcendatei.|
|**Benutzerdefiniert**|Öffnet die **neue benutzerdefinierte Ressource** Dialogfeld, in dem Sie eine benutzerdefinierte Ressource erstellen können. Benutzerdefinierte Ressourcen sind nur im Binär-Editor bearbeitet werden.|

Verwenden der **neue benutzerdefinierte Ressource** erstellen eine neue benutzerdefinierte Ressource in einem C++-Projekt mit der folgenden Eigenschaft im Dialogfeld:

|Eigenschaft|Beschreibung|
|-|-|
|**Ressourcentyp**|Stellt ein Textfeld zum Eingeben der Namen von einem benutzerdefinierten Ressourcentyp. Visual C++ nutzt den Namen automatisch beim Beenden der **neue benutzerdefinierte Ressource** Dialogfeld.|

### <a name="to-create-a-new-resource"></a>So erstellen Sie eine neue Ressource

Sie können eine neue Ressource, die mithilfe der folgenden erstellen:

- In **Ressourcenansicht**, wählen Sie die RC-Datei, und wählen Sie dann die **bearbeiten** Menü, und wählen Sie **Ressource hinzufügen**. In der **Ressource hinzufügen** Dialogfeld Wählen Sie den Typ der Ressource, die Sie Ihrem Projekt hinzufügen möchten.

   > [!TIP]
   > Sie können auch mit der rechten Maustaste in der RC-Datei **Ressourcenansicht** , und wählen Sie **Ressource hinzufügen** aus dem Kontextmenü.

- In **Projektmappen-Explorer**mit der rechten Maustaste auf den Projektordner, und wählen Sie **hinzufügen**, wählen Sie dann **Ressource hinzufügen** im Kontextmenü auf. In der **Ressource hinzufügen** Dialogfeld Wählen Sie den Typ der Ressource, die Sie Ihrem Projekt hinzufügen möchten.

   > [!NOTE]
   > Wenn Sie noch keine RC-Datei in Ihrem Projekt haben, wird in diesem Schritt eine erstellt. Anschließend können Sie diesen Schritt wiederholen, um der neuen RC-Datei spezifische Ressourcentypen hinzuzufügen.

- In [Klassenansicht](/visualstudio/ide/viewing-the-structure-of-code)mit der rechten Maustaste auf die Klasse, und wählen Sie **hinzufügen**. Wählen Sie **Ressource hinzufügen** aus dem Kontextmenü, und wählen Sie den Typ der Ressource, die Sie Ihrem Projekt hinzufügen möchten.

- In der **Projekt** Menü wählen **Ressource hinzufügen**.

## <a name="create-a-resource-template"></a>Erstellen Sie eine Ressourcenvorlage

Eine Ressourcenvorlage ist eine benutzerdefinierte Ressource, die Sie als RCT-Datei gespeichert haben. Eine Ressourcenvorlage dient dann als Ausgangspunkt zum Erstellen von Ressourcen. Ressourcenvorlagen sparen Zeit bei der Entwicklung von zusätzlichen Ressourcen oder Gruppen von Ressourcen, die Freigabe von Funktionen wie Standardsteuerelemente oder Elemente wiederholt. Beispielsweise wenn eine Schaltfläche "Hilfe", mit einem Unternehmens-Logo-Symbol in mehreren Dialogfeldern angezeigt werden sollen, erstellen Sie eine neue Dialogfeldvorlage, und passen Sie sie mit der Schaltfläche "Hilfe" und das Logo.

Nachdem die Ressourcenvorlage angepasst haben, speichern Sie die Änderungen im Vorlagenordner (oder im Includepfad angegebenen Speicherort), damit die neue Ressourcenvorlage unter ihrem Ressourcentyp im angezeigt werden, wird die **Ressource hinzufügen** im Dialogfeld. Sie können jetzt die neue Ressourcenvorlage beliebig oft verwenden, je nach Bedarf.

> [!NOTE]
> Der Ressourcen-Editor stellt automatisch eine eindeutige Ressourcen-ID bereit. Sie können Überarbeiten der [Ressourceneigenschaften](../windows/changing-the-properties-of-a-resource.md) je nach Bedarf.

> [!NOTE]
> Platzieren Sie sprachspezifische Vorlagendateien in Unterverzeichnissen des zentralen Vorlagenverzeichnisses. Platzieren Sie z. B. nur Englisch-Vorlagendateien im... \\< ressourcenvorlagenverzeichnis\>\1033. Visual Studio, die für die neue RCT-Dateien unter \Programme\Microsoft Visual Studio sucht \<Version\>\VC\VCResourceTemplates, unter \Programme\Microsoft Visual Studio \<Version > \VC\VCResourceTemplates\\< LCID\> (z. B. 1033 für Englisch), *oder* überall auf der [Includepfad](../windows/how-to-specify-include-directories-for-resources.md). Wenn Sie die RCT-Dateien in einen anderen Speicherort, z. B. "Dokumente" speichern möchten, müssen Sie dieser Ordner dem Includepfad hinzugefügt wird, damit Visual Studio die RCT-Datei gefunden werden kann.

### <a name="to-create-a-resource-template"></a>Zum Erstellen einer Ressourcenvorlage

1. In **Projektmappen-Explorer**, mit der rechten Maustaste in Ihrem Projekts.

1. Wählen Sie im Kontextmenü den Befehl **hinzufügen**, wählen Sie dann **neues Element hinzufügen**.

1. In der **neues Element hinzufügen** Dialogfeld die **Vorlagen:** wählen Sie im Bereich **Ressourcenvorlagendatei (.rct)**.

1. Geben Sie einen Namen und Speicherort für die neue RCT-Datei, und wählen Sie **öffnen**.

   Die neue RCT-Datei wird dem Projekt hinzugefügt und wird im **Projektmappen-Explorer** unter der **Ressourcen** Ordner.

1. Doppelklicken Sie auf die RCT-Datei, um sie in einem Dokumentfenster zu öffnen. Um Ressourcen hinzuzufügen, mit der rechten Maustaste in der Datei im Dokumentfenster, und wählen Sie **Ressource hinzufügen**.

   Sie können diese Ressourcen anpassen und speichern die RCT-Datei.

### <a name="to-convert-an-existing-resource-file-to-a-template"></a>Um eine vorhandene Ressourcendatei in eine Vorlage konvertieren

1. Öffnen Sie die RC-Datei als eigenständige Datei.

1. Auf der **Datei** , wählen Sie im Menü **speichern \< *Filename*> als**.

1. Geben Sie einen Speicherort aus, und wählen Sie **OK**.

### <a name="to-create-a-new-resource-from-a-template"></a>So erstellen Sie eine neue Ressource aus einer Vorlage

1. In der **Ressourcenansicht** Bereich mit der rechten Maustaste in der RC-Datei, und wählen Sie **Ressource hinzufügen** aus dem Kontextmenü.

1. In der **Ressource hinzufügen** Dialogfeld wählen das Pluszeichen (**+**) neben einer Ressource, um den Ressourcenknoten zu erweitern und alle Vorlagen für diese Ressource verfügbaren anzeigen.

1. Doppelklicken Sie auf die Vorlage, die Sie verwenden möchten.

1. Ändern Sie die hinzugefügte Ressource nach Bedarf im zugehörigen Ressourcen-Editor.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>
[Ressourcen-Editor](../windows/resource-editors.md)<br/>
[Arbeiten mit Ressourcendateien](../windows/working-with-resource-files.md)<br/>
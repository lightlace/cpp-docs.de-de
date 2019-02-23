---
title: 'Vorgehensweise: Erstellen von Ressourcen (C++)'
ms.date: 02/14/2019
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
ms.openlocfilehash: 768675a878891ebb75c7f42c12eae8dfcfa3510b
ms.sourcegitcommit: e540706f4e2675e7f597cfc5b4f8dde648b007bb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/22/2019
ms.locfileid: "56676486"
---
# <a name="how-to-create-resources-c"></a>Vorgehensweise: Erstellen von Ressourcen (C++)

Sie können Ressourcen für das Projekt durch erstellen:

- Verwenden einer Ressourcenskriptdatei. Dieser Schritt ist erforderlich, bevor Sie Ressourcen hinzufügen.

- Hinzufügen von Ressourcen zu Ihrem Projekt ein. Dieser Schritt zeigt, wie Sie mit der **Ressourcenansicht**.

- Mithilfe einer Resource Vorlage zum Erstellen von benutzerdefinierter Ressourcen.

> [!NOTE]
> Die **Ressourcen-Editor-** und **Ressourcenansicht** sind in Express-Editionen nicht verfügbar.

## <a name="use-resource-script-files"></a>Verwenden von Ressourcenskriptdateien

Bevor Sie zu erstellen und Ihrem Projekt neue Ressourcen hinzufügen, müssen Sie zunächst eine Ressourcenskriptdatei (.rc) erstellen.

> [!NOTE]
> Sie können nur ein Ressourcen-Skript zu einem vorhandenen Projekt in Visual Studio-IDE geladen hinzufügen. Sie können keine eigenständige Ressourcenskriptdatei außerhalb des Projekts, erstellen, obwohl Ressourcenvorlagen (RCT-Dateien) können jederzeit erstellt werden.

### <a name="to-create-a-resource-script-file"></a>Zum Erstellen einer Ressourcenskriptdatei

1. Setzen Sie den Fokus auf den vorhandenen Projektordner in **Projektmappen-Explorer**, z. B. *"meinProjekt"*.

   > [!NOTE]
   > Verwechseln Sie nicht mit dem Projektmappenordner im Projektordner **Projektmappen-Explorer**. Wenn Sie den Fokus verschieben, auf die **Lösung** Ordner müssen nicht gleich **neues Element hinzufügen** Optionen.

1. Wechseln Sie zu, klicken Sie im Menü **Projekt** > **neues Element hinzufügen**.

1. Wählen Sie die **Visual C++** Ordner, und wählen Sie **Ressourcendatei (.rc)** im rechten Bereich.

1. Geben Sie einen Namen für die Ressourcenskriptdatei in die **Namen** Textfeld und Sie **öffnen**.

### <a name="to-open-a-resource-script-file"></a>Zum Öffnen einer Ressourcenskriptdatei

Sie können Ressourcen in einer Ressourcenskriptdatei anzeigen, ohne dass ein Projekt zu öffnen. Die Skriptdatei wird geöffnet, in einem Dokumentfenster im Gegensatz zu den **Ressourcenansicht**.

> [!NOTE]
> Einige Befehle sind nur verfügbar, wenn die Datei geöffnet eigenständige, d. h. außerhalb eines Projekts oder ohne das Laden des Projekts ist. Beispielsweise verwenden die **speichern** -Befehl, um eine Datei mit einem anderen Datenformat oder Namen zu speichern, die Datei muss geöffnet eigenständig sein.

- Wechseln Sie zum Öffnen einer Ressourcenskriptdatei außerhalb eines Projekts, klicken Sie im Menü auf **Datei** > **öffnen**, und wählen Sie **Datei**. Navigieren Sie dann auf die Ressourcenskriptdatei, markieren Sie die Datei, und wählen **öffnen**.

  - Verwenden Sie zum Öffnen einer Ressourcenskriptdatei im Textformat den Dropdown-Pfeil rechts von der **öffnen** Schaltfläche im obigen Schritt, und wählen Sie **Öffnen mit**. Wählen Sie dann **Quellcode-Editor (Text)** und von der **öffnen als** Dropdown-Liste **Text**, und die Ressource wird geöffnet, der **Quellcode**Editor.

    > [!NOTE]
    > Gibt es möglicherweise vorkommen, dass Sie die Inhalte der Ressourcenskriptdatei Ihres Projekts ohne Verwendung der Ressourcen-Editor zum Öffnen einer Ressource anzeigen möchten. Beispielsweise möchten Sie möglicherweise nach einer Zeichenfolge über alle Dialogfelder in der Ressourcendatei hinweg suchen, ohne dass Sie dafür jedes einzeln öffnen müssen. Sie können die Ressourcendatei einfach öffnen, im Text-Format, um alle darin enthaltenen Ressourcen anzuzeigen, und führen globale Vorgänge, die von den Text-Editor unterstützt werden.

- Zum Öffnen mehrere Ressource Skripts führen Sie die oben genannten Schritte für jede Datei, die Sie öffnen z. B., möchten *Source1.rc* und *Source2.rc*. Klicken Sie dann, wenn beide RC-Dateien in separaten Dokumentfenstern geöffnet sind, verwenden die **Fenster** Menü oder mit der rechten Maustaste eine der RC-Dateien, und wählen **neue horizontale Registerkartengruppe** oder **neue vertikaler Tabulator Gruppe**. Die Windows werden jetzt nebeneinander angezeigt, damit Sie sie gleichzeitig anzeigen können.

> [!TIP]
> Sie können auch Ressourcenskriptdateien öffnen, mit der rechten Maustaste in die RC-Datei **Projektmappen-Explorer**auswählen **Öffnen mit...**  und **Quellcode-Editor (Text)**.

### <a name="to-edit-a-resource-script-file"></a>Bearbeiten eine Ressourcenskriptdatei

- Wechseln Sie zu, um eine vorhandene Ressourcendatei in eine Vorlage mit der Ressourcenskriptdatei geöffnet ist, klicken Sie im Menü zu konvertieren, **Datei** > **speichern \< *Filename*> als**. Klicken Sie dann einen Speicherort anzugeben, und wählen Sie **OK**.

Beim Erstellen einer Microsoft Foundation Class (MFC)-Anwendung für die Verwendung von Windows die [MFS-Anwendungsassistenten](../mfc/reference/mfc-application-wizard.md), der Assistent generiert eine Reihe grundlegende Dateien, einschließlich einer Ressourcenskriptdatei (.rc)), das die Kernfunktionen von die MFC-Bibliothek enthält. Allerdings sind nicht diese MFC-spezifische Funktionen verfügbar, beim Bearbeiten einer RC-Datei für Windows-Anwendungen, die nicht auf MFC basiert. Dies schließt Code-Assistenten, menüaufforderungen, Auflisten der Inhalte von Kombinationsfeld-Steuerelemente und ActiveX-Steuerelement hostet.

- MFC-Unterstützung in die Ressourcenskriptdatei geöffneten hinzufügen **Ressourcenansicht**, markieren Sie den Ordner "Resources" (z. B. *MFC.rc*). Klicken Sie dann in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window)legen **MFC Mode** zu **"true"**.

  > [!NOTE]
  > Zusätzlich zum Festlegen **MFC Mode**, die RC-Datei muss Teil eines MFC-Projekts. Festlegen der **MFC Mode** zu **"true"** auf eine RC-Datei in einem Win32-Projekt wird nicht bieten Ihnen MFC-Funktionen.

## <a name="create-resources"></a>Erstellen von Ressourcen

Sie können eine Ressource erstellen, als neue Standardressource bedeutet eine Ressource, die basierend auf einer Vorlage wird nicht oder als eine Ressource, die Vorlage.

Verwenden der **Ressourcenansicht** im Projekt enthaltenen Ressourcendateien angezeigt werden soll. Erweitern des obersten Ordners, z. B. *Projekt1.rc*, werden die Ressourcentypen innerhalb dieser Datei. Erweitern Sie die einzelnen Ressourcentyp, um die einzelnen Ressourcen dieses Typs anzuzeigen.

> [!TIP]
> Zum Öffnen der **Ressourcenansicht** Fenster, wechseln Sie zum Menü **Ansicht** > **Ressourcenansicht** , oder drücken Sie **STRG** +  **UMSCHALT**+**E**.

Können Sie mit der rechten Maustaste auf die **Ressourcenansicht** Fenster aus, um ein Kontextmenü mit Befehlen starten, oder doppelklicken Sie auf der Titelleiste und Abdocken des Fensters. Mit der rechten Maustaste in der Titelleiste für zusätzliche Befehle, die das Verhalten des Fensters zu steuern. Weitere Informationen finden Sie unter [Windows Management](/visualstudio/ide/customizing-window-layouts-in-visual-studio).

Die **Ressourcenansicht** Windows enthält die **Ressource hinzufügen** Dialogfeld mit den folgenden Eigenschaften ein C++-Windows-desktop-Anwendungsprojekt Ressourcen hinzugefügt:

| Eigenschaft | Beschreibung |
|---|---|
| **Ressourcentyp** | Geben Sie die Art der Ressource, die Sie erstellen möchten.<br/><br/>Sie können den Cursor und die Kategorien um zusätzliche Ressourcen anzuzeigen, die sich im Visual Studio-...\Microsoft befinden erweitern \<Version\>\VC\VCResourceTemplates\\< LCID\>\mfc.rct. Wenn Sie RCT-Dateien hinzufügen möchten, legen sie hier auf, oder geben Sie ein anderes [Includepfad](../windows/how-to-specify-include-directories-for-resources.md).<br/><br/>Auf der obersten Ebene in der Strukturansicht angezeigte Ressourcen sind die von Visual Studio bereitgestellten Standardressourcen. Ressourcen in RCT-Dateien werden auf der zweiten Ebene der entsprechenden Kategorie angezeigt. Es ist nicht beschränkt auf die Anzahl von RCT-Dateien, die Sie hinzufügen können.<br/><br/> |
| **Neu** | Erstellen Sie eine Ressource, die basierend auf dem Typ, der im ausgewählten der **Ressourcentyp** ein, und öffnen Sie die Ressource im entsprechenden Editor.<br/><br/>Z. B. bei der Erstellung einer Ressource, öffnet es die Ressource in der [Dialog-Editor](../windows/dialog-editor.md). |
| **Importieren** | Öffnen der **importieren** im Dialogfeld auf die Ressource navigieren Sie in das aktuelle Projekt importieren möchten.<br/><br/>Sie können importieren Bitmap-, Symbol-, Cursor, HTML, sound (. WAV), oder benutzerdefinierte Ressourcendatei. |
| **Benutzerdefiniert** | Öffnen der **neue benutzerdefinierte Ressource** Dialogfeld zum Erstellen einer benutzerdefinierten Ressource.<br/><br/>Enthält auch eine **Ressourcentyp** -Eigenschaft, ein Textfeld zur Eingabe der Name der dem benutzerdefinierten Ressourcentyp bereitstellt. Visual C++ nutzt automatisch den Namen beim Beenden.<br/><br/>Benutzerdefinierte Ressourcen sind nur im Binär-Editor bearbeitet werden. |

Wenn Sie eine neue Ressource erstellen, Visual C++ weist einen eindeutigen Namen, z. B. `IDD_Dialog1`. Sie können diese Ressourcen-ID anpassen, indem Sie die Ressourceneigenschaften entweder im zugehörigen Ressourcen-Editor oder im Bearbeiten der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window).

> [!NOTE]
> Geben Sie kein Ressourcenname oder ID, die von Visual Studio reserviert ist. Reservierten Namen lauten `DESIGNINFO`, `HWB`, und `TEXTINCLUDE`, und die reservierte ID ist `255`.

So erstellen Sie eine Ressource verwenden Sie eine der folgenden:

- In **Ressourcenansicht**, wählen Sie die RC-Datei, und verwenden Sie **bearbeiten** > **Ressource hinzufügen** , und wählen Sie den Typ der Ressource, die dem Projekt hinzugefügt.

   > [!TIP]
   > Sie können auch mit der rechten Maustaste in der RC-Datei **Ressourcenansicht** , und wählen Sie **Ressource hinzufügen** aus dem Kontextmenü.

- In **Projektmappen-Explorer**, mit der rechten Maustaste in des Projektordners, wählen Sie **hinzufügen** > **Ressource hinzufügen** , und wählen Sie den Typ der Ressource, die dem Projekt hinzugefügt.

   > [!NOTE]
   > Wenn Sie noch keine RC-Datei in Ihrem Projekt haben, wird in diesem Schritt eine erstellt. Anschließend können Sie diesen Schritt wiederholen, um der neuen RC-Datei spezifische Ressourcentypen hinzuzufügen.

- In [Klassenansicht](/visualstudio/ide/viewing-the-structure-of-code)mit der rechten Maustaste auf die Klasse, wählen Sie **hinzufügen** > **Ressource hinzufügen** , und wählen Sie den Typ der Ressource, die dem Projekt hinzugefügt.

- Verwenden Sie das Menü **Projekt** > **Ressource hinzufügen**.

## <a name="use-resource-templates"></a>Verwenden von Ressourcenvorlagen

Eine Ressourcenvorlage ist eine benutzerdefinierte Ressource, die Sie als RCT-Datei gespeichert haben. Eine Ressourcenvorlage dient dann als Ausgangspunkt zum Erstellen von Ressourcen. Ressourcenvorlagen sparen Zeit bei der Entwicklung von zusätzlichen Ressourcen oder Gruppen von Ressourcen, die Freigabe von Funktionen wie Standardsteuerelemente oder Elemente wiederholt. Beispielsweise wenn eine Schaltfläche "Hilfe", mit einem Unternehmens-Logo-Symbol in mehreren Dialogfeldern angezeigt werden sollen, erstellen Sie eine neue Dialogfeldvorlage, und passen Sie sie mit der Schaltfläche "Hilfe" und das Logo.

Nachdem eine Ressourcenvorlage angepasst haben, speichern Sie die Änderungen im Vorlagenordner oder in dem Includepfad angegebenen Speicherort, damit die neue Ressourcenvorlage unter ihrem Ressourcentyp im angezeigt werden die **Ressource hinzufügen** Dialogfeld. Sie können jetzt die neue Ressourcenvorlage beliebig oft verwenden, je nach Bedarf.

> [!NOTE]
> Der Ressourcen-Editor stellt automatisch eine eindeutige Ressourcen-ID bereit. Sie können Überarbeiten der [Ressourceneigenschaften](../windows/changing-the-properties-of-a-resource.md) je nach Bedarf.

> [!NOTE]
> Platzieren Sie sprachspezifische Vorlagendateien in Unterverzeichnissen des zentralen Vorlagenverzeichnisses. Wechseln Sie z. B. nur auf Englisch verfügbar Vorlagendateien... \\< ressourcenvorlagenverzeichnis\>\1033. Visual Studio, die für die neue RCT-Dateien unter \Programme\Microsoft Visual Studio sucht \<Version\>\VC\VCResourceTemplates, \Programme\Microsoft Visual Studio \<Version > \VC\VCResourceTemplates\\< LCID\> (z. B. LCID 1033 für Englisch), oder eine beliebige Stelle in der [Includepfad](../windows/how-to-specify-include-directories-for-resources.md). Wenn Sie die RCT-Dateien an einem anderen Speicherort speichern möchten, müssen Sie den Speicherort auf dem Includepfad hinzufügen.

### <a name="to-create-and-use-a-resource-template"></a>Erstellen und Verwenden einer Ressourcenvorlage

1. In **Projektmappen-Explorer**, mit der rechten Maustaste in Ihrem Projekts.

1. Wählen Sie im Kontextmenü den Befehl **hinzufügen** > **neues Element hinzufügen**.

1. In der **Vorlagen:** wählen Sie im Bereich **Ressourcenvorlagendatei (.rct)**.

1. Geben Sie einen Namen und Speicherort für die neue RCT-Datei, und wählen Sie **öffnen**.

   Die neue RCT-Datei wird dem Projekt hinzugefügt und wird im **Projektmappen-Explorer** unter der **Ressourcen** Ordner.

1. Doppelklicken Sie auf die RCT-Datei, um sie in einem Dokumentfenster zu öffnen. Um Ressourcen hinzuzufügen, mit der rechten Maustaste in der Datei im Dokumentfenster, und wählen Sie **Ressource hinzufügen**.

   Sie können Ihre hinzugefügten Ressourcen anpassen und speichern die RCT-Datei.

1. In der **Ressourcenansicht** Bereich mit der rechten Maustaste in der RC-Datei, und wählen Sie **Ressource hinzufügen**.

1. Wählen Sie das Pluszeichen (**+**) neben einer Ressource, um den Ressourcenknoten zu erweitern und die für diese Ressource verfügbaren Vorlagen anzuzeigen.

1. Doppelklicken Sie auf die Vorlage, die Sie verwenden möchten.

   Sie können die hinzugefügte Ressource ändern, die Ressourcen-Editor nach Bedarf.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>
[Vorgehensweise: Ressourcen verwalten](../windows/how-to-copy-resources.md)<br/>
[Vorgehensweise: Einfügen von Ressourcen zur Kompilierungszeit](../windows/how-to-include-resources-at-compile-time.md)<br/>
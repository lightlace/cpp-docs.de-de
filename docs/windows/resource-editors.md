---
title: Ressourcen-Editoren (C++)
ms.date: 02/14/2019
f1_keywords:
- vs.editors.resource
- vc.resvw.resource.editors
- vs.resvw.resource.editors
- vs.resourceview
- vc.resvw.resource.previewing
- vs.resvw.resource.previewing
helpviewer_keywords:
- editors [C++], resource
- editors [C++]
- resource editors
- Windows [C++], application resource editing
- resources [C++], viewing
- layouts, previewing resource
- resource editors [C++], viewing resources
- .rc files [C++], viewing resources
- resources [C++], editing
- properties [C++], resources
- resources [C++], properties
ms.assetid: e20a29ec-d6fb-4ead-98f3-431a0e23aaaf
ms.openlocfilehash: aeeca87ceb5b2c5e54da7087b5020ccbc1c39039
ms.sourcegitcommit: 470de1337035dd33682d935b4b6c6d8b1bdb0bbb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2019
ms.locfileid: "56320808"
---
# <a name="resource-editors-c"></a>Ressourcen-Editoren (C++)

Ein **Ressource** -Editor ist eine spezialisierte Umgebung zum Erstellen oder Ändern von Ressourcen, die in einem Visual Studio-Projekt enthalten sind. Die Ressourcen-Editoren von Visual Studio teilen Techniken und Schnittstellen, die Sie beim schnellen und einfachen Erstellen und Ändern von Anwendungsressourcen unterstützen. Ressourcen-Editoren können Sie anzeigen und Bearbeiten von Ressourcen im entsprechenden Ressourcen-Editor und Vorschau.

Wenn Sie eine Ressource erstellen oder öffnen, wird automatisch der entsprechende Editor geöffnet.

> [!NOTE]
> Da verwaltete Projekte keine Ressourcenskriptdateien verwenden, müssen Sie Ihre Ressourcen im Öffnen **Projektmappen-Explorer**. Mit der [Bildbearbeitung](../windows/image-editor-for-icons.md) und dem [Binär-Editor](binary-editor.md) ist die Bearbeitung von Ressourcendateien in verwalteten Projekten möglich. Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Das Bearbeiten eingebetteter Ressourcen wird von den Visual Studio-Ressourcen-Editoren nicht unterstützt.

|Verwenden Sie...|Zur Bearbeitung von...|
|----------------|----------------|
|[Zugriffstasten-Editor](../windows/accelerator-editor.md)|Zugriffstastentabellen in Visual C++-Projekten.|
|[Binary Editor](binary-editor.md)|Binäre Daten und benutzerdefinierte Ressourcen in Visual C++-, Visual Basic- oder Visual C#-Projekten.|
|[Dialog-Editor](../windows/dialog-editor.md)|Dialogfelder in Visual C++-Projekten.|
|[Image Editor](../windows/image-editor-for-icons.md)|Bitmaps, Symbole, Cursor und andere Bilddateien in Visual C++-, Visual Basic- oder Visual C#-Projekten.|
|[Menü-Editor](../windows/menu-editor.md)|Menüressourcen in Visual C++-Projekten.|
|[Ribbon-Editor](../mfc/ribbon-designer-mfc.md)|Menübandressourcen in MFC-Projekten.|
|[Zeichenfolgen-Editor](../windows/string-editor.md)|Zeichenfolgentabellen in Visual C++-Projekten.|
|[Symbolleisten-Editor](../windows/toolbar-editor.md)|Symbolleistenressourcen in Visual C++-Projekten. Der Symbolleisten-Editor ist Teil des Grafik-Editors.|
|[Versionsinfo-Editor](../windows/version-information-editor.md)|Versionsinformationen in Visual C++-Projekten.|

> [!NOTE]
> Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

## <a name="view-and-edit-resources"></a>Anzeigen und Bearbeiten von Ressourcen

Jeder Ressourcentyp hat einen **Ressource** Editor, die speziell für diesen Ressourcentyp. Sie können neu anordnen, ändern Sie die Größe, Steuerelemente und Features hinzufügen oder anderweitig Aspekte einer Ressource mit dem zugehörigen-Editor ändern. Sie können auch eine Ressource in bearbeiten [Textformat](../windows/how-to-open-a-resource-script-file-in-text-format.md) und [Binärformat](../windows/opening-a-resource-for-binary-editing.md).

Einige Ressourcentypen sind einzelne Dateien, die importiert und auf verschiedene Weise verwendet werden können. Dazu gehören, Bitmaps, Symbole, Cursor, Symbolleisten und html-Dateien. Solche Ressourcen müssen Dateinamen und [Ressourcenbezeichner](../windows/symbols-resource-identifiers.md). Andere, befinden sich z. B. Dialogfelder, Menüs und Zeichenfolgentabellen in Win32-Projekte nur als Teil einer Ressourcenskriptdatei (.rc) oder eine Ressourcenvorlagendatei (.rct).

Ressourcen können auch außerhalb des Projekts bearbeitet werden, finden Sie unter [Vorgehensweise: Öffnen eine Ressourcenskriptdatei außerhalb eines Projekts (eigenständig)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).

> [!NOTE]
> Eigenschaften einer Ressource [kann geändert werden, mithilfe des Eigenschaftenfensters](../windows/changing-the-properties-of-a-resource.md).

### <a name="to-edit-the-properties-of-a-resource"></a>So bearbeiten Sie die Eigenschaften einer Ressource

1. In [Ressourcenansicht](../windows/resource-view-window.md), mit der rechten Maustaste in der Ressource, die Sie verwenden möchten, bearbeiten, und wählen **Eigenschaften** aus dem Kontextmenü.

1. In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), ändern Sie die Eigenschaften der Ressource.

### <a name="to-undo-a-change-made-to-the-properties-of-a-resource"></a>Um eine der Eigenschaften einer Ressource vorgenommene Änderung rückgängig zu machen.

1. Stellen Sie sicher, dass die Ressource den Fokus besitzt, **Ressourcenansicht**.

1. Wählen Sie **Rückgängig** aus der **bearbeiten** Menü.

### <a name="win32-resources"></a>Win32-Ressourcen

Sie erreichen die Win32-Ressourcen in der [Ressourcenansicht](../windows/resource-view-window.md) Bereich.

#### <a name="to-view-a-win32-resource-in-a-resource-editor"></a>So zeigen Sie eine Win32-Ressource in einem Ressourcen-Editor an

1. Wählen Sie **Ressourcenansicht** aus der **Ansicht** Menü.

1. Wenn die **Ressourcenansicht** Fenster nicht das oberste Fenster ist die **Ressourcenansicht** Tab, um es in den Vordergrund zu bringen.

1. Von **Ressourcenansicht**, erweitern Sie den Ordner für das Projekt, das Ressourcen enthält, angezeigt werden soll. Wenn Sie eine Ressource anzeigen möchten, erweitern Sie beispielsweise die **Dialogfeld** Ordner.

1. Doppelklicken Sie auf die Ressource ist z. B. **IDD_ABOUTBOX**.

   Die Ressource wird im geeigneten Editor geöffnet. Z. B. für Dialogfeldressourcen, die Ressource geöffnet wird innerhalb der **Dialogfeld** Editor.

   Sie können auch [Ressourcen in einer RC (Ressourcenskript)-Datei anzeigen, ohne dass ein Projekt öffnen](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).

#### <a name="to-delete-an-existing-win-32-resource"></a>So löschen Sie eine vorhandene Win32-Ressource

1. In **Ressourcenansicht**, erweitern Sie den Knoten für einen Ressourcentyp.

1. Mit der rechten Maustaste auf die Ressource, die Sie verwenden möchten, löschen, und wählen **löschen** aus dem Kontextmenü.

   > [!NOTE]
   > Sie können eine Ressource, die den gleichen Befehl im Kontextmenü verwenden, wenn Sie die RC-Datei, die in einem Dokumentfenster außerhalb eines Projekts geöffnet haben, löschen.

### <a name="managed-project-resources"></a>Verwaltete Projektressourcen

Da verwaltete Projekte keine Ressourcenskriptdateien verwenden nicht, müssen Sie Ihre Ressourcen im Öffnen **Projektmappen-Explorer**. Mit der [Bildbearbeitung](../windows/image-editor-for-icons.md) und dem [Binär-Editor](binary-editor.md) ist die Bearbeitung von Ressourcendateien in verwalteten Projekten möglich. Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Die Visual Studio-Ressourcen-Editoren unterstützt nicht das Bearbeiten eingebetteter Ressourcen.

- So zeigen Sie in einer verwalteten Ressource in einem Ressourcen-Editor an **Projektmappen-Explorer**, doppelklicken Sie auf die Ressource ist z. B. *Bitmap1.bmp*.

   Die Ressource wird im geeigneten Editor geöffnet.

- So löschen Sie eine vorhandene verwaltete Ressource in **Projektmappen-Explorer**, mit der rechten Maustaste in der Ressource, die Sie verwenden möchten, löschen, und wählen **löschen** aus dem Kontextmenü.

## <a name="preview-resources"></a>Ressourcen für die Seitenansicht

Vorschau anzeigen Sie, Ihre Ressourcen, um die Ihnen ermöglichen, die grafischen Ressourcen anzeigen, ohne sie zu öffnen. Anzeigen einer Vorschau ist auch nützlich für ausführbare Dateien, nachdem Sie diese kompiliert haben, da die Ressourcen-IDs in Zahlen zu ändern. Da diese numerischen Bezeichnern nicht oft genug Informationen bereitstellen, kann die Vorschau der Ressourcen schnell identifizieren.

Sie können das visuelle Layout der die folgenden Ressourcentypen in Vorschau anzeigen: Bitmap, Dialogfeld "," Symbol "," im Menü "," Cursor ","-Symbolleiste

Die Vorschau-Funktion anwenden nicht auf Ressourcen: Accelerator, Manifest, Zeichenfolgentabelle und Versionsinformationen

> [!NOTE]
> Um eine Vorschau der Ressourcen müssen Win32 aus.

### <a name="to-preview-resources"></a>Vorschau der Ressourcen

1. In [Ressourcenansicht](../windows/resource-view-window.md) oder ein Dokumentfenster, und wählen Sie die Ressource ein, z. B. `IDD_ABOUTBOX`.

1. In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), wählen die **Eigenschaftenseiten** Schaltfläche.

   > [!TIP]
   > Für eine Verknüpfung auf die **Ansicht** , wählen Sie im Menü **Eigenschaftenseiten**.

   Die **Eigenschaftenseite** für die Ressource wird geöffnet, eine Vorschau der jeweiligen Ressource angezeigt. Anschließend können Sie die **einrichten** und **unten** Pfeiltasten, um der Struktur navigieren zu steuern, **Ressourcenansicht** oder das Dokumentfenster. Die **Eigenschaftenseite** bleibt geöffnet und zeigt jede Ressource, die Fokus besitzt und kann in der Vorschau angezeigt werden.

## <a name="requirements"></a>Anforderungen

Keine

## <a name="see-also"></a>Siehe auch

[Arbeiten mit Ressourcendateien](../windows/working-with-resource-files.md)<br/>
[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>
[Ressourcen-IDs (Symbole)](../windows/symbols-resource-identifiers.md)<br/>
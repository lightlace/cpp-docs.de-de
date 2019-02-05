---
title: Anzeigen und Bearbeiten von Ressourcen in einem Ressourcen-Editor (C++)
ms.date: 11/04/2016
f1_keywords:
- vs.resourceview
- vc.resvw.resource.previewing
- vs.resvw.resource.previewing
helpviewer_keywords:
- resources [C++], viewing
- layouts, previewing resource
- resource editors [C++], viewing resources
- .rc files [C++], viewing resources
- resources [C++], editing
- properties [C++], resources
- resources [C++], properties
ms.assetid: ba8bdc07-3f60-43c7-aa5c-d5dd11f0966e
ms.openlocfilehash: 02ab58d37f3f188c3d65740b218cb9b2ac799714
ms.sourcegitcommit: 52c05e10b503e834c443ef11e7ca1987e332f876
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2019
ms.locfileid: "55742660"
---
# <a name="viewing-and-editing-resources-in-a-resource-editor-c"></a>Anzeigen und Bearbeiten von Ressourcen in einem Ressourcen-Editor (C++)

Jeder Ressourcentyp hat einen **Ressource** Editor, die speziell für diesen Ressourcentyp. Sie können neu anordnen, ändern Sie die Größe, Steuerelemente und Features hinzufügen oder anderweitig Aspekte einer Ressource mit dem zugehörigen-Editor ändern. Sie können auch eine Ressource in bearbeiten [Textformat](../windows/how-to-open-a-resource-script-file-in-text-format.md) und [Binärformat](../windows/opening-a-resource-for-binary-editing.md).

Einige Ressourcentypen sind einzelne Dateien, die importiert und auf verschiedene Weise verwendet werden können. Dazu gehören, Bitmaps, Symbole, Cursor, Symbolleisten und html-Dateien. Solche Ressourcen müssen Dateinamen und [Ressourcenbezeichner](../windows/symbols-resource-identifiers.md). Andere, befinden sich z. B. Dialogfelder, Menüs und Zeichenfolgentabellen in Win32-Projekte nur als Teil einer Ressourcenskriptdatei (.rc) oder eine Ressourcenvorlagendatei (.rct).

> [!NOTE]
> Eigenschaften einer Ressource [kann geändert werden, mithilfe des Eigenschaftenfensters](../windows/changing-the-properties-of-a-resource.md).

## <a name="win32-resources"></a>Win32-Ressourcen

Sie erreichen die Win32-Ressourcen in der [Ressourcenansicht](../windows/resource-view-window.md) Bereich.

### <a name="to-view-a-win32-resource-in-a-resource-editor"></a>So zeigen Sie eine Win32-Ressource in einem Ressourcen-Editor an

1. Wählen Sie **Ressourcenansicht** aus der **Ansicht** Menü.

1. Wenn die **Ressourcenansicht** Fenster nicht das oberste Fenster ist die **Ressourcenansicht** Tab, um es in den Vordergrund zu bringen.

1. Von **Ressourcenansicht**, erweitern Sie den Ordner für das Projekt, das Ressourcen enthält, angezeigt werden soll. Wenn Sie eine Ressource anzeigen möchten, erweitern Sie beispielsweise die **Dialogfeld** Ordner.

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

1. Doppelklicken Sie auf die Ressource ist z. B. **IDD_ABOUTBOX**.

   Die Ressource wird im geeigneten Editor geöffnet. Z. B. für Dialogfeldressourcen, die Ressource geöffnet wird innerhalb der **Dialogfeld** Editor.

   Sie können auch [Ressourcen in einer RC (Ressourcenskript)-Datei anzeigen, ohne dass ein Projekt öffnen](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).

### <a name="to-delete-an-existing-win-32-resource"></a>So löschen Sie eine vorhandene Win32-Ressource

1. In **Ressourcenansicht**, erweitern Sie den Knoten für einen Ressourcentyp.

2. Mit der rechten Maustaste auf die Ressource, die Sie verwenden möchten, löschen, und wählen **löschen** aus dem Kontextmenü.

   > [!NOTE]
   > Sie können eine Ressource, die den gleichen Befehl im Kontextmenü verwenden, wenn Sie die RC-Datei, die in einem Dokumentfenster außerhalb eines Projekts geöffnet haben, löschen.

## <a name="resources-in-managed-projects"></a>Ressourcen in verwalteten Projekten

Da verwaltete Projekte keine Ressourcenskriptdateien verwenden nicht, müssen Sie Ihre Ressourcen im Öffnen **Projektmappen-Explorer**. Mit der [Bildbearbeitung](../windows/image-editor-for-icons.md) und dem [Binär-Editor](binary-editor.md) ist die Bearbeitung von Ressourcendateien in verwalteten Projekten möglich. Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Die Visual Studio-Ressourcen-Editoren unterstützt nicht das Bearbeiten eingebetteter Ressourcen.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

### <a name="to-view-a-managed-resource-in-a-resource-editor"></a>So zeigen Sie eine verwaltete Ressource in einem Ressourcen-Editor an

In **Projektmappen-Explorer**, doppelklicken Sie auf die Ressource ist z. B. **Bitmap1.bmp**.

   Die Ressource wird im geeigneten Editor geöffnet.

### <a name="to-delete-an-existing-managed-resource"></a>So löschen Sie eine vorhandene verwaltete Ressource

In **Projektmappen-Explorer**, mit der rechten Maustaste in der Ressource, die Sie verwenden möchten, löschen, und wählen **löschen** aus dem Kontextmenü.

## <a name="changing-the-properties-of-resources"></a>Ändern der Eigenschaften von Ressourcen

### <a name="to-edit-the-properties-of-a-resource"></a>So bearbeiten Sie die Eigenschaften einer Ressource

1. In [Ressourcenansicht](../windows/resource-view-window.md), mit der rechten Maustaste in der Ressource, die Sie verwenden möchten, bearbeiten, und wählen **Eigenschaften** aus dem Kontextmenü.

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

1. In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), ändern Sie die Eigenschaften der Ressource.

### <a name="to-undo-a-change-made-to-the-properties-of-a-resource"></a>Um eine der Eigenschaften einer Ressource vorgenommene Änderung rückgängig zu machen.

1. Stellen Sie sicher, dass die Ressource den Fokus besitzt, **Ressourcenansicht**.

1. Wählen Sie **Rückgängig** aus der **bearbeiten** Menü.

## <a name="previewing-resources"></a>Anzeigen von Ressourcen in der Vorschau

Vorschau anzeigen Sie, Ihre Ressourcen, um die Ihnen ermöglichen, die grafischen Ressourcen anzeigen, ohne sie zu öffnen. Anzeigen einer Vorschau ist auch nützlich für ausführbare Dateien, nachdem Sie diese kompiliert haben, da die Ressourcen-IDs in Zahlen zu ändern. Da diese numerischen Bezeichnern nicht oft genug Informationen bereitstellen, kann die Vorschau der Ressourcen schnell identifizieren.

Sie können das visuelle Layout der die folgenden Ressourcentypen in Vorschau anzeigen:

- Bitmap

- Dialogfeld

- Symbol

- Menü

- Cursor

- Symbolleiste

Die Vorschau-Funktion anwenden nicht auf Accelerator, Manifest, Zeichenfolgentabelle und Versionsinformationen Ressourcen.

### <a name="to-preview-resources"></a>Vorschau der Ressourcen

1. In [Ressourcenansicht](../windows/resource-view-window.md) oder ein Dokumentfenster, und wählen Sie die Ressource ein, z. B. **IDD_ABOUTBOX**.

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

1. In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), wählen die **Eigenschaftenseiten** Schaltfläche.

   \- oder –

   Auf der **Ansicht** , wählen Sie im Menü **Eigenschaftenseiten**.

   Die **Eigenschaftenseite** für die Ressource wird geöffnet, eine Vorschau der jeweiligen Ressource angezeigt. Anschließend können Sie die **einrichten** und **unten** Pfeiltasten, um der Struktur navigieren zu steuern, **Ressourcenansicht** oder das Dokumentfenster. Die **Eigenschaftenseite** bleibt geöffnet und zeigt jede Ressource, die Fokus besitzt und kann in der Vorschau angezeigt werden.

> [!NOTE]
> Um eine Vorschau der Ressourcen müssen Win32 aus.

## <a name="requirements"></a>Anforderungen

Keine

## <a name="see-also"></a>Siehe auch

[Vorgehensweise: Öffnen einer Ressourcenskriptdatei außerhalb eines Projekts (eigenständig)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)<br/>
[Ressourcen-Editor](../windows/resource-editors.md)
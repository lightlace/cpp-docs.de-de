---
title: "Viewing and Editing Resources in a Resource Editor"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vs.resourceview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "resources [Visual Studio], viewing"
  - "rc files, viewing resources"
  - "Resource View pane"
  - "layouts, previewing resource"
  - "code, viewing resources"
  - "resource editors, viewing resources"
  - ".rc files, viewing resources"
  - "resources [Visual Studio], editing"
ms.assetid: ba8bdc07-3f60-43c7-aa5c-d5dd11f0966e
caps.latest.revision: 12
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Viewing and Editing Resources in a Resource Editor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Jeder Ressourcentyp verfügt über einen Ressourcen\-Editor, der für diesen Ressourcentyp spezifisch ist.  Sie können Steuerelemente und Features neu anordnen, verkleinern bzw. vergrößern oder hinzufügen und Aspekte einer Ressource mit dem zugehörigen Editor anderweitig ändern.  Ressourcen können auch im [Textformat](../windows/how-to-open-a-resource-script-file-in-text-format.md) und [Binärformat](../mfc/opening-a-resource-for-binary-editing.md) bearbeitet werden.  
  
 Einige Ressourcentypen sind einzelne Dateien, die importiert und vielfältig verwendet werden können. Dazu gehören Bitmaps, Symbole, Cursor, Symbolleisten und HTML\-Dateien.  Derartige Ressourcen verfügen sowohl über Dateinamen als auch über [Ressourcenbezeichner](../mfc/symbols-resource-identifiers.md).  Andere Ressourcen, z. B. Dialogfelder, Menüs und Zeichenfolgentabellen in Win32\-Projekten, sind nur als Teil einer Ressourcenskriptdatei \(**.rc**\) oder einer Ressourcenvorlagendatei \(**.rct**\) verfügbar.  
  
> [!NOTE]
>  Eigenschaften einer Ressource [können mithilfe des Eigenschaftenfensters geändert werden](../windows/changing-the-properties-of-a-resource.md).  
  
## Win32\-Ressourcen  
 Um auf Win32\-Ressourcen zuzugreifen, können Sie das Fenster [Ressourcenansicht](../windows/resource-view-window.md) verwenden.  
  
#### So zeigen Sie eine Win32\-Ressource in einem Ressourcen\-Editor an  
  
1.  Wählen Sie im Menü **Ansicht** die Option **Ressourcenansicht** aus.  
  
2.  Wenn die Ressourcenansicht nicht im Vordergrund angezeigt wird, klicken Sie auf die Registerkarte **Ressourcenansicht**, um das Fenster in den Vordergrund zu verschieben.  
  
3.  Erweitern Sie im Bereich **Ressourcenansicht** den Ordner für das Projekt, dessen Ressourcen Sie anzeigen möchten.  Wenn Sie z. B. eine Dialogfeldressource anzeigen möchten, erweitern Sie den Dialogordner.  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC\-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
4.  Doppelklicken Sie auf die Ressource, z. B. auf **IDD\_ABOUTBOX**.  
  
     Die Ressource wird im geeigneten Editor geöffnet.  Bei Dialogfeldressourcen wird die Ressource z. B. im Dialog\-Editor geöffnet.  
  
     Sie können [Ressourcen auch in einer RC\-Datei \(Ressourcenskript\) anzeigen, ohne dass ein Projekt geöffnet ist](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
#### So löschen Sie eine vorhandene Win32\-Ressource  
  
1.  Erweitern Sie in der Ressourcenansicht den Knoten für einen Ressourcentyp.  
  
2.  Klicken Sie mit der rechten Maustaste auf die zu löschende Ressource, und wählen Sie im Kontextmenü den Befehl **Löschen**.  
  
    > [!NOTE]
    >  Eine Ressource kann mit demselben Kontextmenübefehl gelöscht werden, wenn die RC\-Datei in einem Dokumentfenster außerhalb eines Projekts geöffnet ist.  
  
## Ressourcen in verwalteten Projekten  
 Da in verwalteten Projekten keine Ressourcenskriptdateien verwendet werden, müssen Sie die Ressourcen über den **Projektmappen\-Explorer** öffnen.  Mit dem [Grafik\-Editor](../mfc/image-editor-for-icons.md) und dem [Binär\-Editor](../mfc/binary-editor.md) können Sie Ressourcendateien in verwalteten Projekten bearbeiten.  Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln.  Das Bearbeiten eingebetteter Ressourcen wird von den Visual Studio\-Ressourcen\-Editoren nicht unterstützt.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
#### So zeigen Sie eine verwaltete Ressource in einem Ressourcen\-Editor an  
  
1.  Doppelklicken Sie im Projektmappen\-Explorer auf die Ressource, z. B. **Bitmap1.bmp**.  
  
     Die Ressource wird im geeigneten Editor geöffnet.  
  
#### So löschen Sie eine vorhandene verwaltete Ressource  
  
1.  Klicken Sie im Projektmappen\-Explorer mit der rechten Maustaste auf die zu löschende Ressource, und wählen Sie im Kontextmenü den Befehl **Löschen**.  
  
### Anforderungen  
 None  
  
## Siehe auch  
 [Resource Editors](../mfc/resource-editors.md)
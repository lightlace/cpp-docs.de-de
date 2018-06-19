---
title: Anzeigen und Bearbeiten von Ressourcen in einem Ressourcen-Editor | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vs.resourceview
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], viewing
- rc files, viewing resources
- Resource View pane
- layouts, previewing resource
- code, viewing resources
- resource editors, viewing resources
- .rc files, viewing resources
- resources [Visual Studio], editing
ms.assetid: ba8bdc07-3f60-43c7-aa5c-d5dd11f0966e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1afa1377b222789243706cf3c5e61f45b4fcd1a1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891817"
---
# <a name="viewing-and-editing-resources-in-a-resource-editor"></a>Anzeigen und Bearbeiten von Ressourcen in einem Ressourcen-Editor
Jeder Ressource verfügt über einen Ressourcen-Editor für diesen Ressourcentyp spezifisch. Sie können neu anordnen, Größe, Steuerelemente und Features hinzufügen oder ändern andernfalls Aspekte einer Ressource mit dem Editor zugeordnet. Sie können auch in eine Ressource bearbeiten [Textformat](../windows/how-to-open-a-resource-script-file-in-text-format.md) und [Binärformat](../windows/opening-a-resource-for-binary-editing.md).  
  
 Einige Ressourcentypen sind einzelne Dateien, die nicht importiert und auf verschiedene Weise verwendet werden können. Dazu gehören Bitmaps, Symbole, Cursor, Symbolleisten und html-Dateien. Diese Ressourcen müssen Dateinamen sowie [Ressourcenbezeichner](../windows/symbols-resource-identifiers.md). Andere vorhanden z. B. Dialogfelder, Menüs und Zeichenfolgentabellen in Win32-Projekten können nur als Teil einer Ressourcenskriptdatei (.rc) oder eine Ressourcenvorlagendatei (.rct).  
  
> [!NOTE]
>  Eigenschaften einer Ressource [kann geändert werden, mithilfe des Eigenschaftenfensters](../windows/changing-the-properties-of-a-resource.md).  
  
## <a name="win32-resources"></a>Win32-Ressourcen  
 Sie erreichen die Win32-Ressourcen in der [Ressourcenansicht](../windows/resource-view-window.md) Bereich.  
  
#### <a name="to-view-a-win32-resource-in-a-resource-editor"></a>So zeigen Sie eine Win32-Ressource in einem Ressourcen-Editor an  
  
1.  Wählen Sie **Ressourcenansicht** aus der **Ansicht** Menü.  
  
2.  Wenn das Fenster "Ressourcenansicht" nicht das oberste Fenster ist, klicken Sie auf die **Ressourcenansicht** Tab, um es in den Vordergrund zu bringen.  
  
3.  Ressourcenansicht erweitern Sie den Ordner für das Projekt, das Ressourcen enthält, die Sie anzeigen möchten. Wenn Sie eine Ressource anzeigen möchten, erweitern Sie beispielsweise den Ordner Dialog.  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
4.  Doppelklicken Sie auf die Ressource, z. B. "IDD_ABOUTBOX".  
  
     Die Ressource wird im geeigneten Editor geöffnet. Beispielsweise wird für Ressourcen innerhalb der Dialog-Editor die Ressource geöffnet.  
  
     Sie können auch [Ressourcen in einer RC (Ressourcenskript)-Datei anzeigen, ohne dass ein Projekt öffnen](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
#### <a name="to-delete-an-existing-win-32-resource"></a>So löschen Sie eine vorhandene Win32-Ressource  
  
1.  Erweitern Sie in der Ressourcenansicht den Knoten für einen Ressourcentyp aus.  
  
2.  Mit der rechten Maustaste auf die Ressource, die Sie löschen möchten und wählen **löschen** aus dem Kontextmenü.  
  
    > [!NOTE]
    >  Sie können eine Ressource mit demselben Kontextmenübefehl aus, wenn Sie die RC-Datei, die in einem Dokumentfenster außerhalb eines Projekts geöffnet haben, löschen.  
  
## <a name="resources-in-managed-projects"></a>Ressourcen in verwalteten Projekten  
 Da verwaltete Projekte keine Ressourcenskriptdateien verwenden, müssen Sie Ihre Ressourcen im Öffnen **Projektmappen-Explorer**. Mit der [Bildbearbeitung](../windows/image-editor-for-icons.md) und dem [Binär-Editor](binary-editor.md) ist die Bearbeitung von Ressourcendateien in verwalteten Projekten möglich. Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Das Bearbeiten eingebetteter Ressourcen wird von den Visual Studio-Ressourcen-Editoren nicht unterstützt.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
#### <a name="to-view-a-managed-resource-in-a-resource-editor"></a>So zeigen Sie eine verwaltete Ressource in einer Ressourcen-Editor an  
  
1.  Doppelklicken Sie im Projektmappen-Explorer auf die Ressource, z. B. Bitmap1.bmp.  
  
     Die Ressource wird im geeigneten Editor geöffnet.  
  
#### <a name="to-delete-an-existing-managed-resource"></a>So löschen Sie eine vorhandene verwaltete Ressource  
  
1.  Im Projektmappen-Explorer mit der Maustaste der Ressource, die Sie löschen möchten und wählen **löschen** aus dem Kontextmenü.  
  
### <a name="requirements"></a>Anforderungen  
 Keiner  
  
## <a name="see-also"></a>Siehe auch  
 [Ressourcen-Editor](../windows/resource-editors.md)


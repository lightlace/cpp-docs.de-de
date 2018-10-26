---
title: Öffnen einer Ressource für die Binärbearbeitung (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.binary
dev_langs:
- C++
helpviewer_keywords:
- binary data, editing
- resources [C++], opening for binary editing
ms.assetid: d3cdb0e4-da66-410d-8e49-b29073ff2929
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 256ceee14f38885259da11453efef8451d34248c
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50068007"
---
# <a name="opening-a-resource-for-binary-editing-c"></a>Öffnen einer Ressource für die Binärbearbeitung (C++)

### <a name="to-open-a-windows-desktop-resource-for-binary-editing"></a>So öffnen Sie eine Windows-Desktopressource zur Binärbearbeitung

1. Wählen Sie in der [Ressourcenansicht](../windows/resource-view-window.md)die bestimmte Ressourcendatei aus, die Sie bearbeiten möchten.

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. Klicken Sie mit der rechten Maustaste auf die Ressource, und klicken Sie im Kontextmenü auf **Binärdaten öffnen** .

   > [!NOTE]
   > Bei Verwendung der [Ressourcenansicht](../windows/resource-view-window.md) Fenster aus, um eine Ressource in einem Format zu öffnen, dass Visual Studio nicht (etwa eine RCDATA- oder eine benutzerdefinierte Ressource), die Ressource erkennt wird automatisch geöffnet, der **binäre** Editor.

### <a name="to-open-a-managed-resource-for-binary-editing"></a>So öffnen Sie eine verwaltete Ressource für die Binärbearbeitung

1. In **Projektmappen-Explorer**, wählen Sie die bestimmte Ressourcendatei, die Sie bearbeiten möchten.

2. Klicken Sie mit der rechten Maustaste auf die Ressource, und wählen Sie im Kontextmenü **Öffnen mit** aus.

3. Wählen Sie im Dialogfeld **Öffnen mit** den **Binär-Editor**aus.

   > [!NOTE]
   > Mit der [Bildbearbeitung](../windows/image-editor-for-icons.md) und dem [Binär-Editor](binary-editor.md) ist die Bearbeitung von Ressourcendateien in verwalteten Projekten möglich. Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Das Bearbeiten eingebetteter Ressourcen wird von den Visual Studio-Ressourcen-Editoren nicht unterstützt.

   > [!NOTE]
   > Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

![Binär-Editor](../mfc/media/vcbinaryeditor2.gif "vcBinaryEditor2")<br/>
Binärdaten für ein Dialogfeld in der Darstellung im Binär-Editor

Nur bestimmte ASCII-Werte werden im Binär-Editor dargestellt (0x20 bis 0x7E). Erweiterte Zeichen werden im Bereich „ASCII-Wert“ des Binär-Editors (dem rechten Bereich) als Punkte dargestellt. Die "druckbaren" Zeichen sind die ASCII-Werte 32 bis 126.

> [!NOTE]
> Wenn Sie verwenden möchten. die **binäre** -Editor auf eine Ressource, die bereits in einem anderen Editorfenster bearbeitet wird schließen Sie zuerst das andere Editorfenster.

## <a name="requirements"></a>Anforderungen

Keiner

## <a name="see-also"></a>Siehe auch

[Binary Editor](binary-editor.md)
---
title: Ressourcen-Editoren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vs.editors.resource
- vc.resvw.resource.editors
- vs.resvw.resource.editors
dev_langs:
- C++
helpviewer_keywords:
- editors [C++], resource
- editors [C++]
- resource editors
- Windows [C++], application resource editing
ms.assetid: e20a29ec-d6fb-4ead-98f3-431a0e23aaaf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d05557b6f92fa5bce8506572fd1c651950d6aa23
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42594292"
---
# <a name="resource-editors"></a>Ressourcen-Editor

Ein **Ressource** -Editor ist eine spezialisierte Umgebung zum Erstellen oder Ändern von Ressourcen, die in einem Visual Studio-Projekt enthalten sind. Die Ressourcen-Editoren von Visual Studio teilen Techniken und Schnittstellen, die Sie beim schnellen und einfachen Erstellen und Ändern von Anwendungsressourcen unterstützen. Mithilfe von Ressourcen-Editoren können Sie [Ressourcen im entsprechenden Editor anzeigen und bearbeiten](../windows/viewing-and-editing-resources-in-a-resource-editor.md) sowie [Ressourcen in der Vorschau anzeigen](../windows/previewing-resources.md).

Wenn Sie eine Ressource erstellen oder öffnen, wird automatisch der entsprechende Editor geöffnet.

**Hinweis** Da verwaltete Projekte keine Ressourcenskriptdateien verwenden, müssen Sie Ihre Ressourcen im **Projektmappen-Explorer**öffnen. Mit der [Bildbearbeitung](../windows/image-editor-for-icons.md) und dem [Binär-Editor](binary-editor.md) ist die Bearbeitung von Ressourcendateien in verwalteten Projekten möglich. Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Das Bearbeiten eingebetteter Ressourcen wird von den Visual Studio-Ressourcen-Editoren nicht unterstützt.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

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

## <a name="requirements"></a>Anforderungen

Keiner

## <a name="see-also"></a>Siehe auch

[Arbeiten mit Ressourcendateien](../windows/working-with-resource-files.md)  
[Ressourcendateien](../windows/resource-files-visual-studio.md)  
[Symbole: Ressourcenbezeichner](../windows/symbols-resource-identifiers.md)  
[Menüs und weitere Ressourcen](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)
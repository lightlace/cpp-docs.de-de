---
title: Ressourcendateien (Visual Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio]
- .rc files
- resource files
- resource script files
- resource script files, Win-32 based applications
- resource script files, files updated when editing resources
- resources [Visual Studio], types of resource files
- rct files
- resources [C++]
- rc files
- resource files, types of
- .rct files
- resource script files, unsupported types
ms.assetid: 4d2b6fcc-07cf-4289-be87-83a60f69533c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e07849c151cf2e361324a83b86bf98c24525f4ce
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601575"
---
# <a name="resource-files-visual-studio"></a>Ressourcendateien (Visual Studio)

> [!NOTE]
> Diese Materialien beziehen sich auf Windows-Desktopanwendungen. Weitere Informationen zu Ressourcen in die universelle Windows-Plattform-apps finden Sie unter [Definieren von App-Ressourcen](http://msdn.microsoft.com/476ea844-632c-4467-9ce3-966be1350dd4).
>
> Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).
>
> Da Projekte in .NET-Programmiersprachen keine Ressourcenskriptdateien verwenden, müssen Sie Ihre Ressourcen im **Projektmappen-Explorer**. Mit der [Bildbearbeitung](../windows/image-editor-for-icons.md) und dem [Binär-Editor](binary-editor.md) ist die Bearbeitung von Ressourcendateien in verwalteten Projekten möglich. Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Das Bearbeiten eingebetteter Ressourcen wird von den Visual Studio-Ressourcen-Editoren nicht unterstützt.

Der Begriff „Ressourcendatei“ kann sich auf verschiedene Dateitypen beziehen, einschließlich dieser:

- Die Ressourcenskriptdatei (RC) eines Programms.

- Eine Ressourcenvorlagendatei (RCT).

- Eine einzelne Ressource, die als eigenständige Datei vorliegt, wie etwa eine Bitmap-, eine Symbol- oder eine Cursordatei, auf die von einer RC-Datei verwiesen wird.

- Eine von der Entwicklungsumgebung generierte Headerdatei, beispielsweise „Resource.h“, auf die von einer RC-Datei verwiesen wird.

Ressourcen können auch in [anderen Dateitypen](../windows/editable-file-types-for-resources.md) vorkommen, wie z. B. EXE, DLL und RES-Dateien. Sie können mit Ressourcen und Ressourcendateien aus Ihrem Projekt arbeiten, aber auch mit solchen, die nicht Teil Ihres aktuellen Projekts sind. Sie können auch mit Ressourcendateien arbeiten, die nicht in der Entwicklungsumgebung von Visual Studio erstellt wurden. Sie haben unter anderem folgende Möglichkeiten:

- Arbeiten mit geschachtelten und bedingt eingeschlossenen Ressourcendateien.

- Aktualisieren vorhandener Ressourcen oder Konvertierung vorhandener Ressourcen in das Visual C++-Format.

- Importieren oder Exportieren grafischer Ressourcendateien in die oder aus der aktuelle(n) Ressourcendatei.

- Einschließen gemeinsam verwendeter oder schreibgeschützter Bezeichner (Symbole), die von der Entwicklungsumgebung nicht geändert werden können.

- Einschließen von Ressourcen in eine ausführbare Datei (EXE), die im Rahmen des aktuellen Projekts keine Bearbeitung erfordern (oder deren Bearbeitung Sie nicht wünschen), wie etwa bei Ressourcen, die von mehreren Projekten gemeinsam verwendet werden.

- Einschließen von Ressourcentypen, die von der Entwicklungsumgebung nicht unterstützt werden.

In diesem Abschnitt:

- [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md)

- [Erstellen einer neuen Ressource](../windows/how-to-create-a-resource.md)

- [Anzeigen von Ressourcen in einer Ressourcenskriptdatei](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)

- [Öffnen einer Ressourcenskriptdatei im Textformat](../windows/how-to-open-a-resource-script-file-in-text-format.md)

- [Einschließen von Ressourcen zur Kompilierungszeit](../windows/how-to-include-resources-at-compile-time.md)

- [Kopieren von Ressourcen](../windows/how-to-copy-resources.md)

- [Verwenden von Ressourcenvorlagen (RCT)](../windows/how-to-use-resource-templates.md)

- [Importieren und Exportieren von Ressourcen](../windows/how-to-import-and-export-resources.md)

- [Editierbare Dateitypen für Ressourcen](../windows/editable-file-types-for-resources.md)

- [Von der Ressourcenbearbeitung betroffene Dateien](../windows/files-affected-by-resource-editing.md)

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcen-Editor](../windows/resource-editors.md)  
[Arbeiten mit Ressourcendateien](../windows/working-with-resource-files.md)  
[Menüs und weitere Ressourcen](http://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)
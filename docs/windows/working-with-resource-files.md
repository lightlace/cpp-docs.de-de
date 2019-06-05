---
title: Arbeiten mit Ressourcendateien (C++)
ms.date: 02/14/2019
helpviewer_keywords:
- resources [C++], about resources
- resources [C++], about resource files
- resource files [C++], about resource files
ms.assetid: 2699a539-b369-4b78-80f0-df03eb7b6780
ms.openlocfilehash: 09a85231f871ef1a21b2f2adb309d94bb4a29e1a
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504506"
---
# <a name="working-with-resource-files"></a>Arbeiten mit Ressourcendateien

> [!WARNING]
> Dieser Abschnitt gilt für in C++ erstellte Windows-Desktopanwendungen.
>
> Informationen zu Ressourcen in die universelle Windows-Plattform-apps, die in C++ geschrieben wurden, finden Sie unter [Definieren von App-Ressourcen](/windows/uwp/app-resources/), oder zum Hinzufügen von Ressourcen für C++ / CLI (verwaltet)-Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in .NET Framework Developer's Guide.

Ressourcen können aus einer Vielzahl von Elementen, wie bestehen:

- Elemente der Benutzeroberfläche, die Informationen für den Benutzer, z. B. eine Bitmap, Symbol oder Cursor bereitstellen.
- Benutzerdefinierte Ressourcen, die Daten und Anwendungen enthalten muss.
- Versionsressourcen, die von Setup-APIs verwendet werden.
- Menü- und Dialogfeldressourcen.

Sie können Ihrem Projekt neue Ressourcen hinzufügen und diese mit dem entsprechenden Ressourcen-Editor ändern. Die meisten Visual C++-Assistenten generieren automatisch ein RC-Datei für Ihr Projekt.

> [!NOTE]
> Die **Ressourcen-Editoren** und **Ressourcenansicht** sind in Express-Editionen nicht verfügbar.

Um das manuelle Hinzufügen von Ressourcendateien zu verwalteten Projekten finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Dieser Artikel enthält, wie Sie Zugriff auf Ressourcen anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften.

Globalisieren und Lokalisieren von Ressourcen in verwalteten apps, finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="in-this-section"></a>In diesem Abschnitt

[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>
Beschreibt, Ressourcendateien und wie sie in der Windows-desktop-Anwendungen verwendet werden. Außerdem bietet Links zu Artikeln, die beschreiben, wie die Ressourcendateien verwendet.

[Ressourcenbezeichner (Symbole)](../windows/symbols-resource-identifiers.md)<br/>
Beschreiben Symbole und bieten Informationen zur Verwendung des Dialogfelds **Ressourcensymbole** , um Symbole in Ihren Projekten zu verwalten.

[Ressourcen-Editor](../windows/resource-editors.md)<br/>
Beschreibt die Ressourcen-Editoren, bereitgestellt in Visual Studio und die Arten von Ressourcen, die Sie mit jedem Editor ändern können. Enthält auch Links zu detaillierten Informationen über einen Editor ein.

## <a name="related-sections"></a>Verwandte Abschnitte

[C++ in Visual Studio](../overview/visual-cpp-in-visual-studio.md)<br/>
Enthält Links zur Visual C++-Dokumentation

[Sprechen Sie mit uns](/visualstudio/ide/talk-to-us)<br/>
Bietet Links zu Informationen über die Verwendung des Dokumentationssatzes, Support-Kontaktdaten sowie über die Bereitstellung von Barrierefreiheitsfunktionen.

## <a name="see-also"></a>Siehe auch

[Windows-Desktop-Anwendungen](../windows/windows-desktop-applications-cpp.md)<br/>
[Menüs und weitere Ressourcen](/windows/desktop/menurc/resources)
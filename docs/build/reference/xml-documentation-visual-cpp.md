---
title: XML-Dokumentation (Visual C++)
ms.date: 11/04/2016
helpviewer_keywords:
- XML documentation
- XML, documentation comments in source code
- comments, C++ source code files
- /// delimiter for C++ documentation
ms.assetid: a1aec1c5-b2d1-4c74-83ae-1dbbbb76b506
ms.openlocfilehash: d111d601d966ec5f863d62d9788654101a2ab56d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57825526"
---
# <a name="xml-documentation-visual-c"></a>XML-Dokumentation (Visual C++)

Sie können Ihrem Quellcode in Visual C++ Kommentare hinzufügen, die in eine XML-Datei verarbeitet werden. Die Datei kann dann als Eingabe für einen Prozess verwendet werden, der die Klassen im Code dokumentiert.

XML-Dokumentationskommentare in einer Visual C++-Codedatei müssen sich direkt vor einer Methoden- oder Typdefinition befinden. Die Kommentare können dazu verwendet werden, den Datentipp der IntelliSense-QuickInfo in den folgenden Szenarios aufzufüllen:

1. Wenn der Code als Komponente der Windows-Runtime mit einer zugehörigen WINMD-Datei kompiliert wurde.

1. Wenn der Quellcode im aktuellen Projekt enthalten ist.

1. In einer Bibliothek, deren Typdeklarationen und Implementierungen sich in der gleichen Headerdatei befinden.

> [!NOTE]
>  Im aktuellen Release werden Codekommentare in Vorlagen oder beliebigen Elementen, die einen Vorlagentyp enthalten (z.B. eine Funktion, die einen Parameter als Vorlage verwendet), nicht verarbeitet. Das Hinzufügen solcher Kommentare führt zu nicht definiertem Verhalten.

Ausführliche Informationen über das Erstellen einer XML-Datei mit Dokumentationskommentaren finden Sie in den folgenden Themen.

|Weitere Informationen zu|Siehe|
|---------------------------|---------|
|Die zu verwendenden Compileroptionen|[/doc](doc-process-documentation-comments-c-cpp.md)|
|Tags, die Sie zum Bereitstellen häufig verwendeter Funktionen in Dokumentationen verwenden können.|[Empfohlene Tags für Dokumentationskommentare](recommended-tags-for-documentation-comments-visual-cpp.md)|
|ID-Zeichenfolgen, die der Compiler erstellt, um die Konstrukte in Ihrem Code zu identifizieren.|[Verarbeiten der XML-Datei](dot-xml-file-processing.md)|
|Trennen von Dokumentationstags|[Trennzeichen für Visual C++-Dokumentationstags](delimiters-for-visual-cpp-documentation-tags.md)|
|Generieren einer XML-Datei aus mindestens einer XDC-Datei|[XDCMake-Verweis](xdcmake-reference.md)|
|Links zu Informationen über XML im Bezug auf Visual Studio-Featurebereiche|[XML in Visual Studio](/visualstudio/xml-tools/xml-tools-in-visual-studio)|

Wenn Sie XML-Sonderzeichen in den Text eines Dokumentationskommentars einfügen müssen, müssen Sie XML-Entitäten oder einen CDATA-Abschnitt verwenden.

## <a name="see-also"></a>Siehe auch

[Komponentenerweiterungen für Laufzeitplattformen](../../windows/component-extensions-for-runtime-platforms.md)

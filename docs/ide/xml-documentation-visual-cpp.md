---
title: XML-Dokumentation (Visual C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- XML documentation
- XML, documentation comments in source code
- comments, C++ source code files
- /// delimiter for C++ documentation
ms.assetid: a1aec1c5-b2d1-4c74-83ae-1dbbbb76b506
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9d763a62edc2f21d8a7669e409c164906c440f1d
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705633"
---
# <a name="xml-documentation-visual-c"></a>XML-Dokumentation (Visual C++)
Sie können Ihrem Quellcode in Visual C++ Kommentare hinzufügen, die in eine XML-Datei verarbeitet werden. Die Datei kann dann als Eingabe für einen Prozess verwendet werden, der die Klassen im Code dokumentiert.  
  
 XML-Dokumentationskommentare in einer Visual C++-Codedatei müssen sich direkt vor einer Methoden- oder Typdefinition befinden. Die Kommentare können dazu verwendet werden, den Datentipp der IntelliSense-QuickInfo in den folgenden Szenarios aufzufüllen:  
  
1.  Wenn der Code als Komponente der Windows-Runtime mit einer zugehörigen WINMD-Datei kompiliert wurde.  
  
2.  Wenn der Quellcode im aktuellen Projekt enthalten ist.  
  
3.  In einer Bibliothek, deren Typdeklarationen und Implementierungen sich in der gleichen Headerdatei befinden.  
  
> [!NOTE]
>  Im aktuellen Release werden Codekommentare in Vorlagen oder beliebigen Elementen, die einen Vorlagentyp enthalten (z.B. eine Funktion, die einen Parameter als Vorlage verwendet), nicht verarbeitet. Das Hinzufügen solcher Kommentare führt zu nicht definiertem Verhalten.  
  
 Ausführliche Informationen über das Erstellen einer XML-Datei mit Dokumentationskommentaren finden Sie in den folgenden Themen.  
  
|Weitere Informationen zu|Siehe|  
|---------------------------|---------|  
|Die zu verwendenden Compileroptionen|[/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)|  
|Tags, die Sie zum Bereitstellen häufig verwendeter Funktionen in Dokumentationen verwenden können.|[Empfohlene Tags für Dokumentationskommentare](../ide/recommended-tags-for-documentation-comments-visual-cpp.md)|  
|ID-Zeichenfolgen, die der Compiler erstellt, um die Konstrukte in Ihrem Code zu identifizieren.|[Verarbeiten der XML-Datei](../ide/dot-xml-file-processing.md)|  
|Trennen von Dokumentationstags|[Trennzeichen für Visual C++-Dokumentationstags](../ide/delimiters-for-visual-cpp-documentation-tags.md)|  
|Generieren einer XML-Datei aus mindestens einer XDC-Datei|[XDCMake-Verweis](../ide/xdcmake-reference.md)|  
|Links zu Informationen über XML im Bezug auf Visual Studio-Featurebereiche|[XML in Visual Studio](/visualstudio/xml-tools/xml-tools-in-visual-studio)|  
  
 Wenn Sie XML-Sonderzeichen in den Text eines Dokumentationskommentars einfügen müssen, müssen Sie XML-Entitäten oder einen CDATA-Abschnitt verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)
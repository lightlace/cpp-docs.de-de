---
title: XML-Dokumentation (Visual C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- XML documentation
- XML, documentation comments in source code
- comments, C++ source code files
- /// delimiter for C++ documentation
ms.assetid: a1aec1c5-b2d1-4c74-83ae-1dbbbb76b506
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 17853a43d3a94be779b659b0da825467fa66f61c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="xml-documentation-visual-c"></a>XML-Dokumentation (Visual C++)
In Visual C++ können Sie den Quellcode Kommentare hinzufügen, die in eine XML-Datei verarbeitet wird. Diese Datei kann dann die Eingabe an einen Prozess, die Dokumentation für die Klassen im Code erstellt.  
  
 In einer Visual C++-Codedatei müssen die XML-Dokumentationskommentare direkt vor einer Methode oder generischen Typ Definition befinden. Die Kommentare können verwendet werden, zum Auffüllen der Intellisense-QuickInfo Datentipp in den folgenden Szenarien:  
  
1.  Wenn der Code als Windows-Runtime-Komponente mit einem zugehörigen winmd-Datei kompiliert wurde  
  
2.  Wenn der Quellcode im aktuellen Projekt enthalten ist  
  
3.  in einer Bibliothek, deren Typdeklarationen und Implementierungen in der gleichen Headerdatei befinden  
  
> [!NOTE]
>  In der aktuellen Version werden den Kommentaren im Code auf Vorlagen oder einem beliebigen Element, das einen Vorlagentyp enthält (z. B. Funktion, die einen Parameter als Vorlage) nicht verarbeitet. Diese Kommentare hinzufügen, führt zu nicht definiertem Verhalten.  
  
 Weitere Informationen zum Erstellen einer XML-Datei mit dem Dokumentationskommentare finden Sie in den folgenden Themen.  
  
|Weitere Informationen zu|Siehe|  
|---------------------------|---------|  
|Die Compileroptionen verwendet|[/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)|  
|Tags, die Sie verwenden können, um häufig bereitzustellen verwendete Funktionalität in Dokumentation|[Empfohlene Tags für Dokumentationskommentare](../ide/recommended-tags-for-documentation-comments-visual-cpp.md)|  
|Die ID-Zeichenfolgen, die der Compiler erzeugt wird, um die Konstrukte im Code zu identifizieren.|[Verarbeiten der XML-Datei](../ide/dot-xml-file-processing.md)|  
|Gewusst wie: Dokumentationstags begrenzen|[Trennzeichen für Visual C++-Dokumentationstags](../ide/delimiters-for-visual-cpp-documentation-tags.md)|  
|Generieren eine XML-Datei aus einer oder mehreren XDC-Dateien.|[XDCMake-Verweis](../ide/xdcmake-reference.md)|  
|Links zu Informationen über XML, wie er bezieht sich auf Visual Studio-Funktionsbereiche|[XML-Code in Visual Studio](/visualstudio/xml-tools/xml-tools-in-visual-studio)|  
  
 Wenn in diesem Fall müssen Sie eine XML-Sonderzeichen im Text eines Kommentars Dokumentation zu entwickeln, müssen Sie die XML-Entitäten oder einem CDATA-Abschnitt verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)
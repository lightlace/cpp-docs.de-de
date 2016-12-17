---
title: "XML-Dokumentation (Visual C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "///-Trennzeichen für C++-Dokumentation"
  - "Kommentare, C++-Quellcodedateien"
  - "XML-Dokumentation"
  - "XML, Dokumentationskommentare im Quellcode"
ms.assetid: a1aec1c5-b2d1-4c74-83ae-1dbbbb76b506
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "mblome"
manager: "ghogen"
---
# XML-Dokumentation (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In Visual C\+\+ können Sie Kommentare Quellcode hinzufügen, der einer XML\-Datei verarbeitet wird.  Diese Datei kann als Eingabe für einen Prozess dann sein, der Dokumentation für die Klassen im Code erstellt.  
  
 In einer Visual C\+\+\-Codedatei müssen sich XML\-Dokumentationskommentare direkt vor einer Methode oder Typdefinition befinden.  Kommentare können verwendet werden, um den IntelliSense\-QuickInfo\-Datentipp in den folgenden Szenarien aufzufüllen:  
  
1.  Wenn der Code wie eine Windows Runtime\-Komponente mit einer begleitenden .winmd\-Datei kompiliert wurde  
  
2.  wenn der Quellcode im aktuellen enthalten ist, fügen Sie  
  
3.  in einer Bibliothek, deren Typdeklarationen und Implementierungen in derselben Headerdatei sind  
  
> [!NOTE]
>  In der aktuellen Version werden Codekommentare auf Vorlagen oder nichts verarbeitet, die einen Vorlagentyp enthalten \(beispielsweise, eine Funktion, die einen Parameter als Vorlage verwendet\).  Das Hinzufügen dieser Kommentare bewirkt nicht definiertes Verhalten.  
  
 Weitere Informationen über das Erstellen einer XML\-Datei mit Dokumentationskommentaren, finden Sie unter folgenden Themen.  
  
|Informationen über|Siehe|  
|------------------------|-----------|  
|Die Compileroptionen zu verwenden|[\/doc](../build/reference/doc-process-documentation-comments-c-cpp.md)|  
|Tags, die Sie verwenden können, um häufig verwendete Funktionen in der Dokumentation bereitzustellen|[Empfohlene Tags für Dokumentationskommentare](../ide/recommended-tags-for-documentation-comments-visual-cpp.md)|  
|Die ID\-Zeichenfolgen, die der Compiler generiert, um die Konstrukte im Code zu identifizieren|[Verarbeiten der XML\-Datei](../ide/dot-xml-file-processing.md)|  
|Erstellen Dokumentationstags getrennt werden|[Trennzeichen für Visual C\+\+\-Dokumentations\-Tags](../ide/delimiters-for-visual-cpp-documentation-tags.md)|  
|Generieren einer XML\-Datei aus einem oder mehreren .xdc\-Dateien.|[XDCMake\-Verweis](../ide/xdcmake-reference.md)|  
|Links zu Informationen über XML, wie es in Visual Studio\-Funktionsbereichen verknüpft|[XML in Visual Studio](../Topic/XML%20Tools%20in%20Visual%20Studio.md)|  
  
 Wenn Sie XML\-Sonderzeichen im Text eines Dokumentationskommentars ablegen müssen, müssen Sie XML\-Entitäten oder einen CDATA\-Abschnitt verwenden.  
  
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)
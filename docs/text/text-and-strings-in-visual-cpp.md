---
title: "Text und Zeichenfolgen in Visual C++"
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
  - "ASCII-Zeichen [C++]"
  - "Zeichensätze [C++]"
  - "Zeichensätze [C++], Informationen zu Zeichensätzen"
  - "Zeichensätze [C++], Außereuropäisch"
  - "Globalisierung [C++]"
  - "Globalisierung [C++], Zeichensätze"
  - "Internationale Anwendungen [C++], Informationen über internationale Anwendungen"
  - "Japanische Zeichen [C++]"
  - "Kanji-Zeichenunterstützung [C++]"
  - "Lokale Zeichensätze [C++]"
  - "Lokalisierung [C++]"
  - "Lokalisierung [C++], Zeichensätze"
  - "MBCS [C++], Internationale Programmierung"
  - "Unterstützung mehrerer Sprachen [C++]"
  - "Außereuropäische Zeichen [C++]"
  - "Portabilität [C++]"
  - "Portabilität [C++], Zeichensätze"
  - "[C++]-Programmierung, International"
  - "Übersetzen von Code [C++]"
  - "Übersetzung [C++], Zeichensätze"
  - "Unicode [C++]"
ms.assetid: a1bb27ac-abe5-4c6b-867d-f761d4b93205
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "ghogen"
manager: "ghogen"
---
# Text und Zeichenfolgen in Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein wichtiger Aspekt bei der Entwicklung von Anwendungen für internationale Märkte ist die korrekte Darstellung lokaler Zeichensätze.  Mit dem ASCII\-Zeichensatz werden Zeichen im Bereich zwischen 0 x 00 und 0 x 7 F definiert.  Von anderen Zeichensätzen \(hauptsächlich europäischer Herkunft\) werden wie beim ASCII\-Zeichensatz die Zeichen innerhalb des Bereichs von 0 x 00 bis 0 x 7 F definiert; zusätzlich wird ein erweiterter Zeichensatz im Bereich von 0 x 80 bis 0 x FF definiert.  Daher ist ein Einzelbyte\-Zeichensatz \(Single\-Byte Character Set, SBCS\) mit 8 Bits ausreichend, um den ASCII\-Zeichensatz sowie viele andere Zeichensätze für europäische Sprachen darzustellen.  Einige außereuropäische Zeichensätze, z. B. das japanische Kanji, enthalten jedoch so viele Zeichen, dass sie nicht mehr in Einzelbytecodierung dargestellt werden können. Sie müssen daher mit einem Mehrbyte\-Zeichensatz \(Multibyte Character Set, MBCS\) codiert werden.  
  
## In diesem Abschnitt  
 [Unicode und MBCS](../text/unicode-and-mbcs.md)  
 Beschreibt die Visual C\+\+\-Unterstützung für Unicode und MBCS\-Programmierung.  
  
 [Unterstützung für Unicode](../text/support-for-unicode.md)  
 Beschreibt Unicode, eine Spezifikation zur Unterstützung sämtlicher Zeichensätze, einschließlich Zeichensätzen, zu deren Darstellung mehr als ein Byte erforderlich ist.  
  
 [Unterstützung von Mehrbyte\-Zeichensätzen \(MBCS\) in Visual C\+\+](../text/support-for-multibyte-character-sets-mbcss.md)  
 Beschreibt MBCS, eine Alternative zu Unicode für die Unterstützung von Zeichensätzen, die nicht mit einem Byte pro Zeichen dargestellt werden können, z. B. Japanisch und Chinesisch.  
  
 [Zuordnungen für generischen Text in Tchar.h](../text/generic-text-mappings-in-tchar-h.md)  
 Enthält Microsoft\-spezifische Zuordnungen für generischen Text für viele Datentypen, Routinen und andere Objekte.  
  
 [Gewusst wie: Konvertieren zwischen verschiedenen Zeichenfolgentypen](../text/how-to-convert-between-various-string-types.md)  
 Veranschaulicht, wie verschiedene Visual C\+\+\-Zeichenfolgentypen in andere Zeichenfolgen konvertiert werden.  
  
## Verwandte Abschnitte  
 [Internationalisierung](../c-runtime-library/internationalization.md)  
 Beschreibt die internationale Unterstützung in der C\-Laufzeitbibliothek.  
  
 [Internationale Beispiele](assetId:///aa8d390c-cf4c-4dd8-9dea-74d81f93f2f8)  
 Enthält Verknüpfungen mit Beispielen, die die Internationalisierung in Visual C\+\+ demonstrieren.  
  
 [Zeichenfolgen in Sprach\- und Länder\-\/Regionseinstellungen](../c-runtime-library/locale-names-languages-and-country-region-strings.md)  
 Stellt die Zeichenfolgen in Sprach\- und Länder\-\/Regionseinstellungen in der C\-Laufzeitbibliothek bereit.
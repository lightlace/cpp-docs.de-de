---
title: Text und Zeichenfolgen in Visual C++ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- globalization [C++], character sets
- programming [C++], international
- multiple language support [C++]
- Unicode [C++]
- international applications [C++], about international applications
- portability [C++]
- translation [C++], character sets
- non-European characters [C++]
- character sets [C++]
- globalization [C++]
- Japanese characters [C++]
- Kanji character support [C++]
- local character sets [C++]
- ASCII characters [C++]
- character sets [C++], about character sets
- localization [C++], character sets
- translating code [C++]
- localization [C++]
- character sets [C++], non-European
- portability [C++], character sets
- MBCS [C++], international programming
ms.assetid: a1bb27ac-abe5-4c6b-867d-f761d4b93205
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ed4232c73122e797a3b0e7aa17c43cde5ab47cf5
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610713"
---
# <a name="text-and-strings-in-visual-c"></a>Text und Zeichenfolgen in Visual C++
Ein wichtiger Aspekt bei der Entwicklung von Anwendungen für internationale Märkte ist die korrekte Darstellung lokaler Zeichensätze. Mit dem ASCII-Zeichensatz werden Zeichen im Bereich zwischen 0 x 00 und 0 x 7 F definiert. Von anderen Zeichensätzen (hauptsächlich europäischer Herkunft) werden wie beim ASCII-Zeichensatz die Zeichen innerhalb des Bereichs von 0 x 00 bis 0 x 7 F definiert; zusätzlich wird ein erweiterter Zeichensatz im Bereich von 0 x 80 bis 0 x FF definiert. Daher ist ein Einzelbyte-Zeichensatz (Single-Byte Character Set, SBCS) mit 8 Bits ausreichend, um den ASCII-Zeichensatz sowie viele andere Zeichensätze für europäische Sprachen darzustellen. Einige außereuropäische Zeichensätze, z. B. das japanische Kanji, enthalten jedoch so viele Zeichen, dass sie nicht mehr in Einzelbytecodierung dargestellt werden können. Sie müssen daher mit einem Mehrbyte-Zeichensatz (Multibyte Character Set, MBCS) codiert werden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Unicode und MBCS](../text/unicode-and-mbcs.md)  
 Beschreibt die Visual C++-Unterstützung für Unicode und MBCS-Programmierung.  
  
 [Unterstützung für Unicode](../text/support-for-unicode.md)  
 Beschreibt Unicode, eine Spezifikation zur Unterstützung sämtlicher Zeichensätze, einschließlich Zeichensätzen, zu deren Darstellung mehr als ein Byte erforderlich ist.  
  
 [Unterstützung von Mehrbyte-Zeichensätzen (MBCS)](../text/support-for-multibyte-character-sets-mbcss.md)  
 Beschreibt MBCS, eine Alternative zu Unicode für die Unterstützung von Zeichensätzen, die nicht mit einem Byte pro Zeichen dargestellt werden können, z. B. Japanisch und Chinesisch.  
  
 [Zuordnungen für generischen Text in Tchar.h](../text/generic-text-mappings-in-tchar-h.md)  
 Enthält Microsoft-spezifische Zuordnungen für generischen Text für viele Datentypen, Routinen und andere Objekte.  
  
 [Vorgehensweise: Konvertieren zwischen verschiedenen Zeichenfolgentypen](../text/how-to-convert-between-various-string-types.md)  
 Veranschaulicht, wie verschiedene Visual C++-Zeichenfolgentypen in andere Zeichenfolgen konvertiert werden.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Internationalisierung](../c-runtime-library/internationalization.md)  
 Beschreibt die internationale Unterstützung in der C-Laufzeitbibliothek.  
  
 [Internationale Beispiele](http://msdn.microsoft.com/aa8d390c-cf4c-4dd8-9dea-74d81f93f2f8)  
 Enthält Verknüpfungen mit Beispielen, die die Internationalisierung in Visual C++ demonstrieren.  
  
 [Zeichenfolgen in Sprach- und Länder-/Regionseinstellungen](../c-runtime-library/locale-names-languages-and-country-region-strings.md)  
 Stellt die Zeichenfolgen in Sprach- und Länder-/Regionseinstellungen in der C-Laufzeitbibliothek bereit.
---
title: Aktivierung der internationalen Programmierung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- globalization [C++], character sets
- strings [C++], international enabling
- localization [C++], character sets
- MBCS [C++], enabling
- Unicode [C++], enabling
ms.assetid: b077f4ca-5865-40ef-a46e-d9e4d686ef21
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2f4edcae610f17409c319c7b4bd39dc137e1211e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="international-enabling"></a>Aktivierung der Internationalen Programmierung
Den meisten herkömmlichen C- und C++-Code Annahmen zu Zeichen und zeichenfolgenbearbeitung, die nicht gut für internationale Anwendungen funktionieren. MFC und die Laufzeitbibliothek Unicode oder MBCS zu unterstützen, besteht noch immer Arbeit für Sie ausführen. Dieser Abschnitt erläutert Sie leitet die Bedeutung von "Aktivierung der internationalen Programmierung" in Visual C++:  
  
-   Unicode und MBCS mittels portable Datentypen in MFC-Funktion Parameterlisten aktiviert sind und Rückgabetypen. Diese Typen sind in der entsprechenden Möglichkeiten, je nachdem, ob Ihr Build das Symbol definiert bedingt definiert **_UNICODE** bzw. das Symbol **_MBCS** (d. h. DBCS). Unterschiedliche Varianten der MFC-Bibliotheken werden automatisch mit der Anwendung verknüpft, je nachdem, die welche dieser beiden Symbole der Build definiert.  
  
-   Klassenbibliothekscode werden portable Laufzeitfunktionen und auf andere Weise verwendet, um die richtige Unicode oder MBCS-Verhalten zu gewährleisten.  
  
-   Weiterhin müssen Sie bestimmte Arten von Aufgaben Internationalisierung im Code behandeln:  
  
    -   Verwenden Sie die gleichen portable-Laufzeit-Funktionen, die MFC portable unter entweder Umgebung vornehmen.  
  
    -   Stellen von Zeichenfolgenliteralen und Zeichen portable unter entweder Umgebung mithilfe der **_T** Makro. Weitere Informationen finden Sie unter [Zuordnungen für generischen Text in Tchar.h](../text/generic-text-mappings-in-tchar-h.md).  
  
    -   Vorsichtsmaßnahmen Sie beim Analysieren von Zeichenfolgen unter MBCS. Diese Vorsichtsmaßnahmen sind unter Unicode nicht erforderlich. Weitere Informationen finden Sie unter [Tipps für die MBCS-Programmierung](../text/mbcs-programming-tips.md).  
  
    -   Achten Sie darauf, wenn in Ihrer Anwendung die Mischen von ANSI (8-Bit) und (16-Bit) Unicodezeichen. Es ist möglich, verwenden Sie die ANSI-Zeichen in einigen Teilen des Programms und Unicode-Zeichen in anderen, jedoch kann nicht in die gleiche Zeichenfolge kombinieren.  
  
    -   Führen Sie keine hartcodierten Zeichenfolgen in Ihrer Anwendung. Stattdessen richten sie STRINGTABLE-Ressourcen durch die Anwendung RC-Datei hinzugefügt. Die Anwendung kann dann ohne quellcodeänderungen oder Neukompilierung lokalisiert werden. Weitere Informationen zu STRINGTABLE-Ressourcen finden Sie unter [Zeichenfolgen-Editor](../windows/string-editor.md).  
  
> [!NOTE]
>  Zeichensätze für Europäische und MBCS haben einige Zeichen, z. B. Buchstaben mit Akzent, deren Zeichencodes größer als 0 x 80. Da der Großteil des Codes mit Vorzeichen Zeichen verwendet werden, diese Zeichen größer als 0 x 80 sind signaturerweitert bei der Konvertierung in `int`. Dies ist ein Problem für die Arrayindizierung, da die signaturerweitert Zeichen negativ ist, außerhalb des Arrays indiziert. Sprachen, die MBCS verwenden, z. B. Japanisch verwenden, sind ebenfalls eindeutig. Da ein Zeichen von 1 oder 2 Bytes bestehen kann, sollten Sie immer beide Bytes gleichzeitig bearbeiten.  
  
## <a name="see-also"></a>Siehe auch  
 [Unicode und MBCS](../text/unicode-and-mbcs.md)   
 [Strategien für die Internationalisierung](../text/internationalization-strategies.md)
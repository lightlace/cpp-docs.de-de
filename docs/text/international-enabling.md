---
title: Aktivierung der Internationalen Programmierung
ms.date: 11/04/2016
helpviewer_keywords:
- globalization [C++], character sets
- strings [C++], international enabling
- localization [C++], character sets
- MBCS [C++], enabling
- Unicode [C++], enabling
ms.assetid: b077f4ca-5865-40ef-a46e-d9e4d686ef21
ms.openlocfilehash: 4476b0805c8806d344a9290ba190aed7c7697a8f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514633"
---
# <a name="international-enabling"></a>Aktivierung der Internationalen Programmierung

Die meisten herkömmlichen C- und C++-Code Annahmen zum Zeichen und zeichenfolgenbearbeitung, die nicht gut für internationale Anwendungen funktionieren. Während sowohl für MFC-als auch für die Laufzeitbibliothek Unicode oder MBCS unterstützen, ist immer noch Arbeit für Sie ausführen. In diesem Abschnitt wird die Bedeutung von "Aktivierung der internationalen Programmierung" um Sie zu leiten, Visual C++ erläutert:

- Unicode und MBCS mittels portable Datentypen in der Parameterliste von MFC-Funktion aktiviert sind, und Rückgabetypen. Diese Typen werden bedingt definiert, auf die entsprechende Weise, je nachdem, ob Ihr Build das Symbol definiert `_UNICODE` oder Symbol `_MBCS` (bedeutet, dass DBCS). Verschiedene Varianten von MFC-Bibliotheken werden automatisch mit Ihrer Anwendung verknüpft, je nachdem, die welche dieser zwei Symbole, die Ihren Build definiert.

- Klassenbibliothekscode werden portable Laufzeitfunktionen und andere Weise verwendet, um richtige Unicode oder MBCS-Verhalten sicherzustellen.

- Sie müssen immer noch bestimmte Arten von Tasks für Internationalisierung in Ihrem Code behandeln:

   - Verwenden Sie die gleichen portable Laufzeit-Funktionen, die MFC portable unter entweder Umgebung vornehmen.

   - Stellen von Zeichenfolgenliteralen und Zeichen portable unter beiden-Umgebung mithilfe der `_T` Makro. Weitere Informationen finden Sie unter [Zuordnungen für generischen Text in Tchar.h](../text/generic-text-mappings-in-tchar-h.md).

   - Vorsichtsmaßnahmen Sie bei der Analyse der MBCS-Zeichenfolgen. Diese Vorsichtsmaßnahmen sind unter Unicode nicht erforderlich. Weitere Informationen finden Sie unter [Tipps für die MBCS-Programmierung](../text/mbcs-programming-tips.md).

   - Achten Sie darauf, wenn Sie ANSI (8-Bit) und Unicode (16-Bit)-Zeichen in Ihrer Anwendung mischen. Es ist möglich, ANSI-Zeichen in einigen Teilen des Programms und Unicode-Zeichen in anderen Fällen verwenden, aber Sie können diese nicht in die gleiche Zeichenfolge mischen.

   - Führen Sie die Zeichenfolgen nicht hartcodieren, in Ihrer Anwendung. Stattdessen können stellen Sie diese STRINGTABLE Ressourcen, indem diese RC-Datei der Anwendung hinzugefügt wird. Ihre Anwendung kann dann ohne Änderungen am Quellcode oder Neukompilierung lokalisiert werden. Weitere Informationen zu STRINGTABLE-Ressourcen finden Sie unter [Zeichenfolgen-Editor](../windows/string-editor.md).

> [!NOTE]
>  Zeichensätze für Europäische und MBCS müssen einige Zeichen, z. B. Akzentbuchstaben mit Zeichencodes größer als 0 x 80. Da der Großteil des Codes mit Zeichen verwendet werden, diese größer als 0 x 80 Zeichen sind Vorzeichen erweitert, wenn in konvertiert **Int**. Dies ist ein Problem für die Arrayindizierung, da die signaturerweitert mit Zeichen negativ ist, außerhalb des Arrays indiziert. Sprachen, die MBCS verwenden, z. B. Japanisch, zu verwenden, sind ebenfalls eindeutig. Da ein Zeichen von 1 oder 2 Bytes bestehen kann, sollten Sie immer beide Bytes zur gleichen Zeit bearbeiten.

## <a name="see-also"></a>Siehe auch

[Unicode und MBCS](../text/unicode-and-mbcs.md)<br/>
[Strategien für die Internationalisierung](../text/internationalization-strategies.md)
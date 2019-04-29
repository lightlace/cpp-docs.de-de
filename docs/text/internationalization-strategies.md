---
title: Strategien für die Internationalisierung
ms.date: 11/04/2016
helpviewer_keywords:
- globalization [C++], character sets
- language-portable code [C++]
- MBCS [C++], internationalization strategies
- Windows API [C++], international programming strategies
- Win32 [C++], international programming strategies
- Unicode [C++], globalizing applications
- character sets [C++], international programming strategies
- localization [C++], character sets
ms.assetid: b09d9854-0709-4b9a-a00c-b0b8bc4199b1
ms.openlocfilehash: f8c5cec680072ffa34b1ee0bef9e09231de5f1ac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410628"
---
# <a name="internationalization-strategies"></a>Strategien für die Internationalisierung

Je nach Ziel-Betriebssysteme und Märkte haben Sie mehrere Strategien für die Internationalisierung:

- Ihre Anwendung verwendet Unicode.

   Sie verwenden Unicode-spezifischen Funktionen, und alle Zeichen sind 16 Bit breit (auch wenn Sie ANSI-Zeichen in einigen Teilen des Programms für besondere Zwecke verwenden können). Die C-Laufzeitbibliothek bietet Funktionen, Makros und Datentypen für nur-Unicode-Programmierung. MFC ist komplett Unicode-aktiviert.

- Ihre Anwendung MBCS verwendet und kann auf jede Win32-Plattform ausgeführt werden.

   Sie verwenden die MBCS-spezifische Funktionen. Zeichenfolgen können Einzelbyte-Zeichen, Doppelbytezeichen oder beides enthalten. Die C-Laufzeitbibliothek bietet Funktionen, Makros und Datentypen für die reine MBCS-Programmierung. MFC ist vollständig MBCS-aktiviert.

- Der Quellcode für Ihre Anwendung ist für vollständige Portabilität geschrieben, durch das erneute Kompilieren, mit dem Symbol `_UNICODE` oder Symbol `_MBCS` definiert, können Sie Versionen, die entweder mit erzeugen. Weitere Informationen finden Sie unter [Zuordnungen für generischen Text in tchar.h](../text/generic-text-mappings-in-tchar-h.md).

   Sie verwenden, vollständig portabel C Run-Time-Funktionen, Makros und Datentypen. MFC Flexibilität unterstützt alle diese Strategien.

Der Rest des diese Themen konzentrieren sich auf vollständig portablen Code schreiben, den Sie als Unicode oder MBCS erstellen können.

## <a name="see-also"></a>Siehe auch

[Unicode und MBCS](../text/unicode-and-mbcs.md)<br/>
[Gebietsschemas und Codepages](../text/locales-and-code-pages.md)

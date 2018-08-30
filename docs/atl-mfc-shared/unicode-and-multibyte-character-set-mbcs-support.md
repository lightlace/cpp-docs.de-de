---
title: Legen Sie Unicode- und Multibyte-Zeichensätze (MBCS)-Unterstützung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 1/09/2017
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- MFC [C++], character set support
- MBCS [C++], strings and MFC support
- strings [C++], MBCS support in MFC
- character sets [C++], multibyte
- Unicode [C++], MFC strings
- Unicode [C++], string objects
- strings [C++], Unicode
- strings [C++], character set support
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74f1f0f88828b5d6355c692aa8eaeecd5869bf57
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43202933"
---
# <a name="unicode-and-multibyte-character-set-mbcs-support"></a>Unterstützung für Unicode- und Multibyte-Zeichensätze (MBCS)

Einige Sprachen wie Japanisch und Chinesisch haben große Zeichensätze. Um Programmierung für diese Märkte zu unterstützen, können die Microsoft Foundation Class-Bibliothek (MFC) zwei unterschiedliche Ansätze zum Behandeln von umfangreichen Zeichensätzen:

- [Unicode](#mfc-support-for-unicode-strings), `wchar_t` -basierte Breitzeichen und Zeichenfolgen, die als UTF-16 codiert sind.

- [Multibyte-Zeichensatz-Sätze (MBCS)](#mfc-support-for-mbcs-strings), **Char** Grundlage von einzelnen oder Double-Byte-Zeichen und Zeichenfolgen, die in einem Gebietsschema-spezifische Zeichensatz codiert.

Microsoft empfiehlt sich die Unicode-MFC-Bibliotheken für alle Neuentwicklungen, und die MBCS-Bibliotheken in Visual Studio 2013 und Visual Studio 2015 als veraltet markiert wurden. Dies ist nun nicht mehr der Fall. Die MBCS-Warnungen für veraltete Befehle wurden in Visual Studio 2017 entfernt.

## <a name="mfc-support-for-unicode-strings"></a>MFC-Unterstützung für Unicode-Zeichenfolgen

Die gesamte MFC-Klassenbibliothek wird bedingt für Unicode-Zeichen und Zeichenfolgen in Breitzeichen, die als UTF-16 aktiviert. Insbesondere ist Klasse [CString](../atl-mfc-shared/reference/cstringt-class.md) Unicode-aktiviert.

Diese Bibliothek, Debugger und DLL-Dateien werden verwendet, um Unicode in MFC zu unterstützen:

|||||
|-|-|-|-|
|UAFXCW.LIB|UAFXCW.PDB|UAFXCWD.LIB|UAFXCWD.PDB|
|MFC*Version*U.LIB|MFC*Version*U.PDB|MFC*Version*U.DLL|MFC*Version*UD. LIB|
|MFC*Version*UD. PDB-DATEI|MFC*Version*UD. DLL|MFCS*Version*U.LIB|MFCS*Version*U.PDB|
|MFCS*Version*UD. LIB|MFCS*Version*UD. PDB-DATEI|MFCM*Version*U.LIB|MFCM*Version*U.PDB|
|MFCM*Version*U.DLL|MFCM*Version*UD. LIB|MFCM*Version*UD. PDB-DATEI|MFCM*Version*UD. DLL|

(*Version* stellt die Versionsnummer der Datei ein, z. B. "140" bedeutet, dass Version 14.0.)

`CString` basiert auf dem TCHAR-Datentyp. Wenn _UNICODE-Symbol für einen Build des Programms definiert ist, wird als Typ TCHAR definiert `wchar_t`, eine 16-Bit-Zeichencodierungstyp. Andernfalls TCHAR ist definiert als **Char**, die normale 8-Bit-zeichencodierung. Daher setzt sich ein `CString` unter Unicode aus 16-Bit-Zeichen zusammen. Ohne Unicode wird es besteht aus Zeichen vom Typ **Char**.

Um Unicode-Programmierung der Anwendung durchzuführen, benötigen Sie auch Folgendes:

- Verwenden Sie die _T-Makro, um bedingt codieren Sie Zeichenfolgenliterale, um in Unicode übertragbar sind.

- Wenn Sie Zeichenfolgen übergeben, achten Sie darauf, ob für Funktionsargumente eine bestimmte Länge in Zeichen oder in Bytes erforderlich. Der Unterschied ist wichtig, wenn Sie Unicode-Zeichenfolgen verwenden.

- Verwenden Sie portable Versionen der C-Funktionen zur Behandlung von Zeichenfolgen zur Laufzeit.

- Verwenden Sie die folgenden Datentypen für Zeichen und Zeichenzeiger:

   - Verwenden Sie hier Sie verwenden TCHAR **Char**.

   - Verwenden Sie hier Sie verwenden LPTSTR **Char**<strong>\*</strong>.

   - Verwenden Sie hier Sie verwenden LPCTSTR **const Char**<strong>\*</strong>. `CString` Stellt den Operator LPCTSTR zum Konvertieren zwischen `CString` und LPCTSTR.

`CString` stellt außerdem Unicode-kompatible Konstruktoren, Zuweisungsoperatoren und Vergleichsoperatoren bereit.

Die [Run-Time Library Reference](../c-runtime-library/c-run-time-library-reference.md) definiert portable Versionen aller seiner Funktionen zur Zeichenfolgenbehandlung. Weitere Informationen finden Sie unter der Kategorie [Internationalisierung](../c-runtime-library/internationalization.md).

## <a name="mfc-support-for-mbcs-strings"></a>MFC-Unterstützung für MBCS-Zeichenfolgen

Die Klassenbibliothek wird auch für Multibyte-Zeichensätze, jedoch nur für Doppelbyte-Zeichensätze (DBCS) aktiviert.

In einem Multibyte-Zeichensatz kann ein Zeichen ein oder zwei Bytes breit sein. Wenn es zwei Bytes breit ist, ist sein erstes Byte ein spezielles "führendes Byte", das je nach verwendeter Codepage aus einem bestimmten Bereich ausgewählt wird. Zusammen angewendet, geben die führenden und die "nachfolgenden Bytes" eine eindeutige Zeichencodierung an.

Wenn das Symbol _MBCS für einen Build des Programms definiert ist, geben Sie TCHAR, auf dem `CString` basiert, wird dem **Char**. Sie bestimmen, welche Bytes in einer `CString` führende Bytes und welche nachfolgende Bytes sind. Die Zubehörfunktionen der C-Laufzeitbibliothek unterstützen Sie dabei.

Unter DBCS kann eine angegebene Zeichenfolge alle Einzelbyte-ANSI-Zeichen, alle Doppelbytezeichen oder eine Kombination der beiden enthalten. Diese Methoden erfordern besondere Sorgfalt beim Parsen von Zeichenfolgen. Hierzu gehören `CString`-Objekte.

> [!NOTE]
> Mit der Serialisierung von Unicode-Zeichenfolgen in MFC können sowohl Unicode als auch MBCS-Zeichenfolgen unabhängig von der Version der Anwendung, die Sie ausführen, gelesen werden. Die Datendateien sind zwischen Unicode- und MBCS-Versionen des Programms übertragbar.

`CString`-Memberfunktionen verwenden spezielle Versionen der C-Laufzeitfunktionen mit "generischem Text", die aufgerufen werden, oder sie verwenden Unicode-kompatible Funktionen. Wenn daher eine `CString`-Funktion normalerweise `strcmp` aufrufen würde, ruft sie stattdessen die entsprechende Funktion `_tcscmp` für generischen Text auf. Je nachdem, wie die Symbole _MBCS und _UNICODE definiert sind `_tcscmp` folgendermaßen zugeordnet:

|||
|-|-|
|_MBCS definiert|`_mbscmp`|
|_UNICODE definiert|`wcscmp`|
|Kein Symbol definiert|`strcmp`|

> [!NOTE]
> Die Symbole _MBCS und _UNICODE schließen sich gegenseitig aus.

Funktionszuordnungen für generischen Text für alle zur Behandlung von Zeichenfolgen-Laufzeitroutinen finden Sie im [C Run-Time Library Reference](../c-runtime-library/c-run-time-library-reference.md). Eine Liste finden Sie unter [Internationalisierung](../c-runtime-library/internationalization.md).

Auf ähnliche Weise `CString` Methoden mit generischen datentypzuordnungen implementiert werden. Um sowohl Unicode als auch MBCS zu aktivieren, verwendet MFC TCHAR für **Char** oder `wchar_t`, LPTSTR für **Char** <strong>\*</strong> oder `wchar_t*`, und LPCTSTR für **const Char** <strong>\*</strong> oder `const wchar_t*`. Diese stellen die richtigen Zuordnungen für Unicode oder MBCS sicher.

## <a name="see-also"></a>Siehe auch

[Zeichenfolgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)  
[Zeichenfolgenbearbeitung](../c-runtime-library/string-manipulation-crt.md)  

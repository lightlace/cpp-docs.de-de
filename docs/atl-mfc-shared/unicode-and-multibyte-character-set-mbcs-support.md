---
title: "Legen Sie Unicode- und Multibyte-Zeichensätze (MBCS)-Support | Microsoft Docs"
ms.custom: 
ms.date: 1/09/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
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
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: adbe6ca25afd31c0aba853fde8b503dc333f63f4
ms.sourcegitcommit: 56f6fce7d80e4f61d45752f4c8512e4ef0453e58
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2018
---
# <a name="unicode-and-multibyte-character-set-mbcs-support"></a>Unterstützung für Unicode- und Multibyte-Zeichensätze (MBCS)

Einige Sprachen wie Japanisch und Chinesisch haben große Zeichensätze. Um Programmierung für diese Märkte zu unterstützen, können die Microsoft Foundation Class-Bibliothek (MFC) zwei unterschiedliche Ansätze zum Behandeln von umfangreichen Zeichensätzen:

- [Unicode](#mfc-support-for-unicode-strings), `wchar_t` basierten Wide-Zeichen und Zeichenfolgen, die als UTF-16 codiert sind.

- [Multibyte-Zeichen-Sätze (MBCS)](#mfc-support-for-mbcs-strings), `char` basierten einfache oder Doppelbyte-Zeichen und Zeichenfolgen, die in einem gebietsschemaspezifischen Zeichensatz codiert.

Microsoft hat die Unicode-MFC-Bibliotheken für alle Neuentwicklungen empfohlen, und die MBCS-Bibliotheken in Visual Studio 2013 und Visual Studio 2015 als veraltet markiert wurden. Dies ist nun nicht mehr der Fall. Die MBCS-veraltungswarnungen wurden in Visual Studio 2017 entfernt.

## <a name="mfc-support-for-unicode-strings"></a>MFC-Unterstützung für Unicode-Zeichenfolgen

Die gesamte MFC-Klassenbibliothek wird bedingt für Unicode-Zeichen und Zeichenfolgen in Breitzeichen als UTF-16 gespeichert aktiviert. Insbesondere ist Klasse [CString](../atl-mfc-shared/reference/cstringt-class.md) Unicode aktiviert ist.

Diese Bibliothek, Debugger und DLL-Dateien werden zur Unterstützung von Unicode in MFC verwendet:

|||||
|-|-|-|-|
|UAFXCW.LIB|UAFXCW.PDB|UAFXCWD.LIB|UAFXCWD.PDB|
|MFC*Version*U.LIB|MFC*Version*U.PDB|MFC*Version*U.DLL|MFC*Version*UD. LIB|
|MFC*Version*UD. PDB-DATEI|MFC*Version*UD. DLL|MFCS*Version*U.LIB|MFCS*Version*U.PDB|
|MFCS*Version*UD. LIB|MFCS*Version*UD. PDB-DATEI|MFCM*Version*U.LIB|MFCM*Version*U.PDB|
|MFCM*Version*U.DLL|MFCM*Version*UD. LIB|MFCM*Version*UD. PDB-DATEI|MFCM*Version*UD. DLL|

(*Version* stellt die Versionsnummer der Datei ein, z. B. "140" bedeutet, dass Version 14.0.)

`CString` basiert auf dem Datentyp `TCHAR`. Wenn das Symbol `_UNICODE` für einen Build des Programms definiert ist, wird `TCHAR` als `wchar_t`-Typ, ein 16-Bit-Zeichencodierungstyp, definiert. Andernfalls wird `TCHAR` als `char`, die normale 8-Bit-Zeichencodierung, definiert. Daher setzt sich ein `CString` unter Unicode aus 16-Bit-Zeichen zusammen. Ohne Unicode wird es aus Zeichen vom Typ `char` zusammengesetzt.

Um Unicode-Programmierung der Anwendung durchzuführen, benötigen Sie auch Folgendes:

- Verwenden Sie das `_T`-Makro, um Zeichenfolgen bedingt so zu kodieren, dass sie in Unicode übertragbar sind.

- Wenn Sie Zeichenfolgen übergeben, achten Sie darauf, ob für Funktionsargumente eine bestimmte Länge in Zeichen oder in Bytes erforderlich. Der Unterschied ist wichtig, wenn Sie Unicode-Zeichenfolgen verwenden.

- Verwenden Sie portable Versionen der C-Funktionen zur Behandlung von Zeichenfolgen zur Laufzeit.

- Verwenden Sie die folgenden Datentypen für Zeichen und Zeichenzeiger:

   - Verwenden Sie `TCHAR` hier verwenden Sie `char`.

   - Verwenden Sie `LPTSTR` hier verwenden Sie `char*`.

   - Verwenden Sie `LPCTSTR` hier verwenden Sie `const char*`. `CString` stellt den Operator `LPCTSTR` zum Konvertieren zwischen `CString` und `LPCTSTR` bereit.

`CString` stellt außerdem Unicode-kompatible Konstruktoren, Zuweisungsoperatoren und Vergleichsoperatoren bereit.

Die [Run-Time Library Reference](../c-runtime-library/c-run-time-library-reference.md) definiert portable Versionen aller Funktionen für die Behandlung von Zeichenfolgen. Weitere Informationen finden Sie unter der Kategorie [Internationalisierung](../c-runtime-library/internationalization.md).

## <a name="mfc-support-for-mbcs-strings"></a>MFC-Unterstützung für MBCS-Zeichenfolgen

Die Klassenbibliothek wird auch für Multibyte-Zeichensätze, jedoch nur für Doppelbyte-Zeichensätze (DBCS) aktiviert.

In einem Multibyte-Zeichensatz kann ein Zeichen ein oder zwei Bytes breit sein. Wenn es zwei Bytes breit ist, ist sein erstes Byte ein spezielles "führendes Byte", das je nach verwendeter Codepage aus einem bestimmten Bereich ausgewählt wird. Zusammen angewendet, geben die führenden und die "nachfolgenden Bytes" eine eindeutige Zeichencodierung an.

Wenn das Symbol `_MBCS` für einen Build des Programms definiert ist, wird der Typ `TCHAR`, auf dem `CString` basiert, `char` zugeordnet. Sie bestimmen, welche Bytes in einer `CString` führende Bytes und welche nachfolgende Bytes sind. Die Zubehörfunktionen der C-Laufzeitbibliothek unterstützen Sie dabei.

Unter DBCS kann eine angegebene Zeichenfolge alle Einzelbyte-ANSI-Zeichen, alle Doppelbytezeichen oder eine Kombination der beiden enthalten. Diese Methoden erfordern besondere Sorgfalt beim Parsen von Zeichenfolgen. Hierzu gehören `CString`-Objekte.

> [!NOTE]
> Mit der Serialisierung von Unicode-Zeichenfolgen in MFC können sowohl Unicode als auch MBCS-Zeichenfolgen unabhängig von der Version der Anwendung, die Sie ausführen, gelesen werden. Die Datendateien sind zwischen Unicode- und MBCS-Versionen des Programms übertragbar.

`CString`-Memberfunktionen verwenden spezielle Versionen der C-Laufzeitfunktionen mit "generischem Text", die aufgerufen werden, oder sie verwenden Unicode-kompatible Funktionen. Wenn daher eine `CString`-Funktion normalerweise `strcmp` aufrufen würde, ruft sie stattdessen die entsprechende Funktion `_tcscmp` für generischen Text auf. Je nachdem, wie die Symbole `_MBCS` und `_UNICODE` definiert werden, wird `_tcscmp` wie folgt zugeordnet:

|||
|-|-|
|`_MBCS` ist defined|`_mbscmp`|
|`_UNICODE` ist defined|`wcscmp`|
|Kein Symbol definiert|`strcmp`|

> [!NOTE]
> Die Symbole `_MBCS` und `_UNICODE` schließen sich gegenseitig aus.

Allgemeintext-funktionszuordnungen für alle von der Laufzeitroutinen für die Behandlung von Zeichenfolgen werden in erläutert [C Run-Time Library Reference](../c-runtime-library/c-run-time-library-reference.md). Eine Liste finden Sie unter [Internationalisierung](../c-runtime-library/internationalization.md).

Auf ähnliche Weise `CString` Methoden mithilfe von generischen textzuordnungen von Datentypen implementiert werden. Zur Ermöglichung von MBCS und Unicode-verwendet MFC `TCHAR` für `char` oder `wchar_t`, `LPTSTR` für `char*` oder `wchar_t*`, und `LPCTSTR` für `const char*` oder `const wchar_t*`. Diese stellen die richtigen Zuordnungen für Unicode oder MBCS sicher.

## <a name="see-also"></a>Siehe auch

[Zeichenfolgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)  
[Zeichenfolgenbearbeitung](../c-runtime-library/string-manipulation-crt.md)  

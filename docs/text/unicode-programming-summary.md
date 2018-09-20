---
title: Zusammenfassung der Unicode-Programmierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Unicode [C++], programming with
- Unicode [C++], MFC and C run-time functions
ms.assetid: a4c9770f-6c9c-447c-996b-980920288bed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d49f87d5709483a36325afa426a790374fc93837
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415810"
---
# <a name="unicode-programming-summary"></a>Zusammenfassung der Unicode-Programmierung

Wenn Sie von MFC- und C-Laufzeitunterstützung für Unicode profitieren möchten, müssen Sie folgende Schritte ausführen:

- Definieren Sie `_UNICODE`.

   Definieren Sie das Symbol `_UNICODE` , bevor Sie ein Programm erstellen.

- Geben Sie den Einstiegspunkt an.

   Auf der **Ausgabe** auf der Seite die **Linker** Ordner des Projekts [Eigenschaftenseiten](../ide/property-pages-visual-cpp.md) (Dialogfeld), legen die **Einstiegspunkt** Symbol `wWinMainCRTStartup`.

- Verwenden Sie portable Laufzeitfunktionen und Typen.

   Verwenden Sie für die Behandlung von Unicode-Zeichenfolgen die richtigen C-Laufzeitfunktionen. Sie können die `wcs` Familie der Funktionen, aber Sie können auch die portablen (aktivierten) `_TCHAR` Makros. Diese Makros sind alle mit dem Präfix `_tcs`; sie ersetzen, eins zu eins, für die `str` Funktionsreihe. Diese Funktionen werden ausführlich beschrieben die [Internationalisierung](../c-runtime-library/internationalization.md) Teil der *Run-Time Library Reference*. Weitere Informationen finden Sie unter [Zuordnungen für generischen Text in Tchar.h](../text/generic-text-mappings-in-tchar-h.md).

   Verwendung `_TCHAR` und die verknüpften portablen Datentypen, die in beschriebenen [-Unterstützung für Unicode](../text/support-for-unicode.md).

- Bearbeiten Sie Zeichenfolgenliterale vorschriftsmäßig.

   Vom Visual C++-Compiler wird ein Zeichenfolgenliteral der Form

    ```cpp
    L"this is a literal string"
    ```

   als Unicode-Zeichenfolge interpretiert. Sie können dasselbe Präfix für Literalzeichen verwenden. Verwenden der `_T` Makro Literalzeichenfolgen generisch zu codieren, damit sie als Unicode-Zeichenfolgen als ANSI-Zeichenfolgen (einschließlich MBCS) ohne Unicode kompiliert. Verwenden Sie z. B. nicht:

    ```cpp
    pWnd->SetWindowText( "Hello" );
    ```

   sondern:

    ```cpp
    pWnd->SetWindowText( _T("Hello") );
    ```

   Mit `_UNICODE` definiert, `_T` übersetzt die literale Zeichenfolge auf das Formular mit dem Präfix L, andernfalls `_T` ohne dieses Präfix übersetzt.

    > [!TIP]
    >  Die `_T` Makro ist identisch mit der `_TEXT` Makro.

- Gehen Sie beim Übergeben von Zeichenfolgenlängen an Funktionen mit Bedacht vor.

   Bei einigen Funktionen muss die Anzahl der Zeichen in einer Zeichenfolge angegeben werden, bei anderen Funktionen die Anzahl der Bytes. Z. B. wenn `_UNICODE` definiert ist, der folgende Aufruf von einem `CArchive` Objekt funktioniert nicht (`str` ist eine `CString`):

    ```cpp
    archive.Write( str, str.GetLength( ) );    // invalid
    ```

   In einer Unicode-Anwendung gibt die Länge die Zeichenanzahl, aber nicht die richtige Byte-Anzahl an, da jedes Zeichen zwei Bytes breit ist. Sie müssen also den obigen Funktionsaufruf wie folgt ändern:

    ```cpp
    archive.Write( str, str.GetLength( ) * sizeof( _TCHAR ) );    // valid
    ```

   Dieser Aufruf gibt fehlerfrei an, wie viele Bytes geschrieben werden sollen.

   Zeichenorientierte MFC-Memberfunktionen arbeiten jedoch im Gegensatz zu Byte-orientierten Memberfunktionen ohne diese zusätzliche Codierung:

    ```cpp
    pDC->TextOut( str, str.GetLength( ) );
    ```

     Für `CDC::TextOut` ist eine Anzahl von Zeichen, nicht eine Anzahl von Bytes erforderlich.

- Verwendung [Fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md) um Unicode-Dateien zu öffnen.

Zusammenfassend bieten MFC und die Laufzeitbibliothek folgende Unterstützung für Unicode-Programmierung:

- Mit Ausnahme der Memberfunktionen für Datenbankklassen sind alle MFC-Funktionen, einschließlich `CString`. `CString` stellt darüber hinaus Unicode/ANSI-Konvertierungsfunktionen bereit.

- Die Laufzeitbibliothek stellt Unicode-Versionen aller Funktionen zur Behandlung von Zeichenfolgen zur Verfügung. (Die Laufzeitbibliothek enthält mit den _tcs-Makros auch portable, für Unicode Dies sind die `_tcs` Makros.)

- TCHAR.h stellt portable Datentypen und die `_T` -Makro zum Übersetzen von Zeichenfolgenliteralen und Zeichen. Weitere Informationen finden Sie unter [Zuordnungen für generischen Text in Tchar.h](../text/generic-text-mappings-in-tchar-h.md).

- Die Laufzeitbibliothek enthält eine Breitzeichen-Version von `main`. Verwendung `wmain` , die Unicode-kompatible Anwendung machen.

## <a name="see-also"></a>Siehe auch

[Unterstützung für Unicode](../text/support-for-unicode.md)
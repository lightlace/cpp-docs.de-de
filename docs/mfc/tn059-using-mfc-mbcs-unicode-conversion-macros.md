---
title: 'TN059: Verwenden von MFC MBCS / Unicode-Umwandlungsmakros'
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.mbcs
helpviewer_keywords:
- MFCANS32.DLL
- Unicode [MFC], conversion macros
- Unicode [MFC], OLE interfaces
- conversion macros [MFC]
- converting Unicode
- MBCS [MFC], conversion macros
- macros [MFC], MBCS conversion macros
- TN059
ms.assetid: a2aab748-94d0-4e2f-8447-3bd07112a705
ms.openlocfilehash: e806cea54fcb1559b7d70b2e7672973501fc0adf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476439"
---
# <a name="tn059-using-mfc-mbcsunicode-conversion-macros"></a>TN059: Verwenden von MFC MBCS/Unicode-Umwandlungsmakros

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

Dieser Hinweis beschreibt, wie die Makros, die für die MBCS/Unicode-Konvertierung, die im AFXPRIV definiert sind. H. Diese Makros sind besonders hilfreich, wenn Ihre Anwendung Abschlüsse direkt mit der OLE-API oder aus irgendeinem Grund, häufig muss für die Konvertierung zwischen Unicode und MBCS.

## <a name="overview"></a>Übersicht

In MFC 3.x, wurde eine spezielle DLL verwendet (MFCANS32. (DLL) für die Konvertierung von Unicode und MBCS automatisch, wenn OLE-Schnittstellen aufgerufen wurden. Diese DLL-Datei wurde eine praktisch transparente Schicht, die OLE-Anwendungen, als wären die OLE-APIs und Schnittstellen MBCS geschrieben werden soll, obwohl sie immer Unicode sind zulässig (außer auf einem Macintosh). Während dieser Ebene praktische war und Anwendungen schnell von Win16 auf Win32 portiert zulässig (MFC-, Microsoft Word, Microsoft Excel und VBA, sind nur einige der Microsoft-Anwendungen, die diese Technologie verwendet), es hatte einen manchmal signifikanten Leistungsgewinn erreicht. Aus diesem Grund MFC 4.x diese DLL-Datei wird nicht verwendet und stattdessen kommuniziert direkt mit der Unicode-OLE-Schnittstellen. Zu diesem Zweck MFC muss in Unicode zu MBCS zu konvertieren, wenn Sie einen Aufruf von OLE-Schnittstelle vornehmen, und oft in MBCS aus Unicode zu konvertieren, wenn Sie eine OLE-Schnittstelle implementieren muss. Um dies effizient und einfach zu behandeln, wurden eine Reihe von Makros erstellt, um diese Konvertierung zu vereinfachen.

Einer der größten Hürden zum Erstellen solcher einen Satz von Makros ist die speicherbelegung. Da die Zeichenfolgen an Stelle konvertiert werden können, muss neue Arbeitsspeicher zum Speichern der konvertierten zugeordnet werden. Dies kann mit Code wie den folgenden erfolgt sind:

```
// we want to convert an MBCS string in lpszA
int nLen = MultiByteToWideChar(CP_ACP,
    0,
    lpszA, -1,
    NULL,
    NULL);

LPWSTR lpszW = new WCHAR[nLen];
MultiByteToWideChar(CP_ACP,
    0,
    lpszA, -1,
    lpszW,
    nLen);

// use it to call OLE here
pI->SomeFunctionThatNeedsUnicode(lpszW);

// free the string
delete[] lpszW;
```

Dieser Ansatz als eine Reihe von Problemen. Das Hauptproblem ist, dass es viel Code ist zu schreiben, testen und Debuggen. Etwas, das einen einfachen Aufruf wurde, ist jetzt wesentlich komplexer. Darüber hinaus ist gibt es eine wichtige Common Language Runtime Mehraufwand auf diese Weise. Speicher muss auf dem Heap reserviert und freigegeben, jedes Mal, wenn eine Konvertierung abgeschlossen ist. Schließlich der obige Code würde müssen haben entsprechende `#ifdefs` für Unicode- und Macintosh-Builds (die diese Konvertierung durchgeführt werden, erfordern keine) hinzugefügt.

Die Projektmappe, die, der wir lassen einfallen, besteht darin einige Makros zu erstellen, die (1) Maske der Unterschied zwischen den verschiedenen Plattformen und (2) verwenden Sie eine effiziente Speicherbelegungsschema und (3) sind einfach zum Einfügen in den vorhandenen Quellcode. Hier ist ein Beispiel für eine der Definitionen aus:

```
#define A2W(lpa) (\
((LPCSTR)lpa == NULL) NULL : (\
    _convert = (strnlen(lpa)+1),\
    AfxA2WHelper((LPWSTR) alloca(_convert*2),
    lpa,
    _convert)\)\)
```

Mit diesem Makro anstelle der oben stehende Code und die Dinge sind wesentlich einfacher:

```
// use it to call OLE here
USES_CONVERSION;
pI->SomeFunctionThatNeedsUnicode(T2OLE(lpszA));
```

Es gibt zusätzliche Aufrufe, in denen Konvertierung ist notwendig, aber verwenden die Makros, die einfach und effektiv.

Die Implementierung jedes Makros verwendet die Funktion "_alloca()" "Arbeitsspeicher aus dem Stapel statt dem Heap belegt. Reservieren von Speicher im Stapel ist wesentlich schneller als die Zuteilung von Arbeitsspeicher auf dem Heap, und der Speicher wird automatisch freigegeben, wenn die Funktion beendet wird. Darüber hinaus die Makros vermeiden Sie Aufrufe `MultiByteToWideChar` (oder `WideCharToMultiByte`) mehr als einmal. Dazu weisen Sie ein wenig mehr Arbeitsspeicher als erforderlich erledigt wird. Wir wissen, dass in mindestens einer MBC konvertiert **WCHAR** und für die einzelnen **WCHAR** haben wir ein Maximum von zwei MBC Bytes. Dabei wird jedoch immer genug etwas häufiger als nötig, zugeordnet wird um die Konvertierung den zweiten Aufruf behandeln, die zweite Aufruf der Konvertierungsfunktion vermieden. Der Aufruf der Hilfsfunktion `AfxA2Whelper` reduziert die Anzahl der Argument-pushvorgängen, die ausgeführt werden müssen, um die Konvertierung auszuführen (Dies führt in kleinere Codeabschnitte optimiert, als wenn sie aufgerufen `MultiByteToWideChar` direkt).

In der Reihenfolge für die Makros Speicherplatz zum Speichern der temporären Länge, ist es erforderlich, deklarieren Sie eine lokale Variable namens _convert, die in jeder Funktion, die hierfür verwendet konvertierungsmakros. Dies erfolgt durch das Makro USES_CONVERSION aufrufen, wie im Beispiel oben zu sehen.

Es gibt sowohl generische konvertierungsmakros und OLE-spezifischen Makros. Diese beiden Sätze von anderen Makro werden nachfolgend beschrieben. Alle Makros befinden sich im AFXPRIV. H.

## <a name="generic-conversion-macros"></a>Generische-Konvertierungsmakros

Generische konvertierungsmakros bilden den zugrunde liegende Mechanismus. Der Makrobeispiel und die Implementierung dargestellt, die im vorherigen Abschnitt A2W, ist eine solche "generischen" Makro. Es ist nicht speziell an OLE verbunden. Der Satz von generischen Makros sind unten aufgeführt:

```
A2CW      (LPCSTR) -> (LPCWSTR)
A2W      (LPCSTR) -> (LPWSTR)
W2CA      (LPCWSTR) -> (LPCSTR)
W2A      (LPCWSTR) -> (LPSTR)
```

Neben dem Text Konvertierungen Weise gibt es Makros und Hilfsfunktionen zum Konvertieren von `TEXTMETRIC`, `DEVMODE`, `BSTR`, und OLE-Zeichenfolgen zugeordnet. Bei diesen Makros wird, würde den Rahmen dieser Diskussion – AFXPRIV finden Sie unter. Für Weitere Informationen zu diesen Makros H.

## <a name="ole-conversion-macros"></a>OLE-Konvertierungsmakros

Der OLE-konvertierungsmakros dienen insbesondere für die Behandlung von Funktionen, die erwarten, dass **OLESTR** Zeichen. Wenn Sie die OLE-Header zu untersuchen, sehen Sie zahlreiche Verweise auf **LPCOLESTR** und **OLECHAR**. Diese Typen werden zum Verweisen auf den Typ der verwendeten Zeichen im OLE-Schnittstellen auf eine Weise, die nicht spezifisch für die Plattform ist. **OLECHAR** ordnet **Char** Win16 und Macintosh-Plattformen und **WCHAR** in Win32.

Um die Anzahl der zu halten **#ifdef** -Direktiven in der MFC-code auf ein Minimum haben wir eine ähnliche Makro für jede Konvertierung, die, an denen OLE-Zeichenfolgen beteiligt sind. Die folgenden Makros werden die am häufigsten verwendet:

```
T2COLE   (LPCTSTR) -> (LPCOLESTR)
T2OLE   (LPCTSTR) -> (LPOLESTR)
OLE2CT   (LPCOLESTR) -> (LPCTSTR)
OLE2T   (LPCOLESTR) -> (LPCSTR)
```

In diesem Fall werden ähnliche Makros zur Durchführung von TEXTMETRIC "," DEVMODE "," BSTR "und" OLE-Zeichenfolgen zugeordnet. AFXPRIV finden Sie unter. H für Weitere Informationen.

## <a name="other-considerations"></a>Andere Überlegungen

Verwenden Sie die Makros, die nicht in einer engen Schleife aus. Beispielsweise möchten nicht Sie die folgende Art von Code zu schreiben:

```
void BadIterateCode(LPCTSTR lpsz)
{
    USES_CONVERSION;
    for (int ii = 0; ii <10000; ii++)
    pI->SomeMethod(ii, T2COLE(lpsz));

}
```

Der obige Code verursachen MB Arbeitsspeicher auf dem Stapel, je nachdem welche den Inhalt der Zeichenfolge zuordnen `lpsz` ist! Es dauert auch die Zeit, um die Zeichenfolge für jede Iteration der Schleife zu konvertieren. Verschieben Sie stattdessen eine solche Konstanten Konvertierungen aus der Schleife:

```
void MuchBetterIterateCode(LPCTSTR lpsz)
{
    USES_CONVERSION;
    LPCOLESTR lpszT = T2COLE(lpsz);

    for (int ii = 0; ii <10000; ii++)
    pI->SomeMethod(ii, lpszT);

}
```

Wenn die Zeichenfolge nicht konstant ist, klicken Sie dann kapseln Sie den Aufruf der Methode in eine Funktion. Dadurch wird die Konvertierung Puffer freigegeben werden, dass Sie jedes Mal. Zum Beispiel:

```
void CallSomeMethod(int ii, LPCTSTR lpsz)
{
    USES_CONVERSION;
    pI->SomeMethod(ii, T2COLE(lpsz));

}

void MuchBetterIterateCode2(LPCTSTR* lpszArray)
{
    for (int ii = 0; ii <10000; ii++)
    CallSomeMethod(ii, lpszArray[ii]);

}
```

Geben Sie das Ergebnis eines die Makros, nie zurück, es sei denn, der zurückgegebene Wert bedeutet eine Kopie der Daten vor der Rückgabe. Dieser Code ist z. B. ungültige:

```
LPTSTR BadConvert(ISomeInterface* pI)
{
    USES_CONVERSION;
    LPOLESTR lpsz = NULL;
    pI->GetFileName(&lpsz);

LPTSTR lpszT = OLE2T(lpsz);

    CoMemFree(lpsz);

return lpszT; // bad! returning alloca memory
}
```

Der obige Code könnte behoben werden, durch Ändern des Rückgabewerts auf etwas, das den Wert kopiert:

```
CString BetterConvert(ISomeInterface* pI)
{
    USES_CONVERSION;
    LPOLESTR lpsz = NULL;
    pI->GetFileName(&lpsz);

LPTSTR lpszT = OLE2T(lpsz);

    CoMemFree(lpsz);

return lpszT; // CString makes copy
}
```

Die Makros sind einfach zu verwenden und einfach in Ihren Code einfügen, aber wie Sie die oben genannten Einschränkungen erkennen können, müssen Sie darauf achten, dass bei ihrer Verwendung.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)


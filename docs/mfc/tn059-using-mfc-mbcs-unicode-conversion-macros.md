---
title: 'TN059: Verwenden von MFC MBCS/Unicode-Umwandlungsmakros | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.mbcs
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 379c5b4fb9ed302ad1ea0167f2b32c30e48ab2bf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384289"
---
# <a name="tn059-using-mfc-mbcsunicode-conversion-macros"></a>TN059: Verwenden von MFC MBCS/Unicode-Umwandlungsmakros
> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis beschreibt, wie die Makros für die MBCS/Unicode-Konvertierung, die in AFXPRIV definiert sind. H. Diese Makros sind besonders hilfreich, wenn Ihre Anwendung Abschlüsse direkt mit der OLE-API oder aus irgendeinem Grund, häufig muss zum Konvertieren zwischen Unicode und MBCS.  
  
## <a name="overview"></a>Übersicht  
 In MFC 3.x, wurde eine spezielle DLL verwendet (MFCANS32. DLL-Datei) konvertieren zwischen Unicode und MBCS automatisch, wenn OLE-Schnittstellen aufgerufen wurden. Diese DLL wurde eine fast transparente Ebene, die OLE-serveranwendungen, als wären die OLE-APIs und Schnittstellen MBCS geschrieben werden, obwohl sie immer Unicode sind zulässig (außer auf Macintosh-Computern). Während dieser Schicht praktische war und erlaubt Anwendungen schnell von Win16 auf Win32 portiert werden (MFC, Microsoft Word, Microsoft Excel und VBA, sind nur einige der Microsoft-Anwendungen, die diese Technologie verwendet), manchmal spürbaren Leistungseinbußen hatte erreicht. Aus diesem Grund MFC 4.x verwendet diese DLL nicht, und stattdessen kommuniziert direkt mit der Unicode-OLE-Schnittstellen. Zu diesem Zweck MFC muss in Unicode in MBCS zu konvertieren, bei einem Aufruf von OLE-Schnittstelle, und muss häufig in MBCS aus Unicode zu konvertieren, wenn Sie eine OLE-Schnittstelle implementieren. Um dies effizient und einfach zu verarbeiten, wurden eine Reihe von Makros erstellt, um diese Konvertierung zu vereinfachen.  
  
 Eine der größten Hürden zum Erstellen einer solchen Menge von Makros ist speicherbelegung. Da die Zeichenfolgen festliegen konvertiert werden können, muss neuer Speicher in der konvertierten Ergebnisse enthalten belegt werden. Dies konnte wurde mit Code etwa wie folgt ausgeführt:  
  
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
  
 Dieser Ansatz als eine Reihe von Problemen. Das Hauptproblem ist, dass sie viel Code zu schreiben, testen und Debuggen. Etwas, das eine einfache Funktionsaufruf wurde, ist nun wesentlich komplexer. Darüber hinaus besteht eine wichtige Common Language Runtime Mehraufwand in diesem Fall. Speicher muss auf dem Heap reserviert und freigegeben, jedes Mal, wenn eine Konvertierung erfolgt. Schließlich der obige Code müssten haben entsprechende `#ifdefs` für Unicode- und Macintosh-Builds (die Konvertierung erfolgen, die nicht erforderlich ist) hinzugefügt.  
  
 Die Lösung, der wir in wurde werden einige Makros erstellen, welche (1) Maske den Unterschied zwischen den verschiedenen Plattformen und (2) verwenden eine effiziente Speicherbelegungsschema und (3) sind einfach So fügen Sie den vorhandenen Quellcode. Hier ist ein Beispiel für eine der Definitionen aus:  
  
```  
#define A2W(lpa) (\  
 ((LPCSTR)lpa == NULL) NULL : (\  
    _convert = (strnlen(lpa)+1),\  
    AfxA2WHelper((LPWSTR) alloca(_convert*2),   
    lpa,
    _convert)\)\)  
```  
  
 Mit diesem Makro anstelle des obigen Codes und die Dinge sind wesentlich einfacher:  
  
```  
// use it to call OLE here  
USES_CONVERSION;  
pI->SomeFunctionThatNeedsUnicode(T2OLE(lpszA));
```  
  
 Zusätzliche Aufrufe, bei denen Konvertierung erforderlich, aber mit den Makros ist einfacher und effektiver, sind vorhanden.  
  
 Die Implementierung jedes Makros verwendet die Funktion "_alloca()" "aus dem Stapel statt dem Heap belegt. Reservieren von Speicher im Stapel ist wesentlich schneller als das belegen von Speicher auf dem Heap, und der Speicher wird automatisch freigegeben, wenn die Funktion beendet wird. Darüber hinaus die Makros vermeiden Sie Aufrufe **MultiByteToWideChar** (oder **WideCharToMultiByte**) mehr als einmal. Dies erfolgt durch das Zuweisen von etwas mehr Arbeitsspeicher als notwendig. Wir wissen, dass eine von Multibytezeichen in höchstens eine Nachricht konvertieren wird **WCHAR** und dass für jede **WCHAR** haben wir ein Maximum von zwei von Multibytezeichen Bytes. Durch das Zuweisen jedoch immer genug etwas mehr als erforderlich ist, wird der Konvertierung den zweiten Aufruf behandeln, die zweite Aufruf der Konvertierungsfunktion vermieden. Der Aufruf an die Hilfsfunktion **AfxA2Whelper** reduziert die Anzahl der Push-Argument Vorgänge, die ausgeführt werden müssen, um die Konvertierung auszuführen (Dies führt zu kompaktem Code, als wenn sie aufgerufen **MultiByteToWideChar**direkt).  
  
 In der Reihenfolge nach für den Makros, um Speicherplatz zum Speichern der temporären Länge, es ist erforderlich, deklarieren Sie eine lokale Variable namens _convert, die dies in jeder Funktion, die tut mithilfe der konvertierungsmakros. Dies erfolgt durch Aufrufen der **USES_CONVERSION** Makro wie im Beispiel oben dargestellt.  
  
 Es gibt generische konvertierungsmakros und bestimmte OLE-Makros. Diese zwei unterschiedliche Makro Sätze werden unten erläutert. Alle Makros befinden im AFXPRIV. H.  
  
## <a name="generic-conversion-macros"></a>Generische Konvertierungsmakros  
 Generische konvertierungsmakros bilden die zugrunde liegenden angibt. Das Makrobeispiel und die Implementierung, die im vorherigen Abschnitt A2W, gezeigt ist eine solche "generische" Makro. Es ist nicht speziell an OLE beziehen. Der Satz von generischen Makros wird im folgenden aufgeführt:  
  
```  
A2CW      (LPCSTR) -> (LPCWSTR)  
A2W      (LPCSTR) -> (LPWSTR)  
W2CA      (LPCWSTR) -> (LPCSTR)  
W2A      (LPCWSTR) -> (LPSTR)  
```  
  
 Neben dem Text Konvertierungen Weise stehen auch Makros und Hilfsfunktionen zum Konvertieren von `TEXTMETRIC`, `DEVMODE`, `BSTR`, und OLE-Zeichenfolgen zugeordnet. Diese Makros sind nicht Gegenstand dieser Diskussion - AFXPRIV finden Sie unter. Für Weitere Informationen zu diesen Makros H.  
  
## <a name="ole-conversion-macros"></a>OLE-Konvertierungsmakros  
 Der OLE-konvertierungsmakros dienen insbesondere für Funktionen, die voraussichtlich zum Behandeln von **OLESTR** Zeichen. Wenn Sie die OLE-Header zu untersuchen, sehen Sie viele Verweise **LPCOLESTR** und **OLECHAR**. Diese Typen dienen zum Verweisen auf den Typ der verwendeten Zeichen im OLE-Schnittstellen auf eine Weise, die nicht spezifisch für die Plattform ist. **OLECHAR** ordnet `char` Win16 und Macintosh-Plattformen und **WCHAR** in Win32.  
  
 Damit bleibt die Anzahl der **#ifdef** Direktiven in der MFC-code auf ein Minimum haben wir eine ähnliche Makro für jede Konvertierung, die, in denen Zeichenfolgen OLE beteiligt sind. Die folgenden Makros werden am häufigsten verwendet:  
  
```  
T2COLE   (LPCTSTR) -> (LPCOLESTR)  
T2OLE   (LPCTSTR) -> (LPOLESTR)  
OLE2CT   (LPCOLESTR) -> (LPCTSTR)  
OLE2T   (LPCOLESTR) -> (LPCSTR)  
```  
  
 Erneut stehen ähnliche Makros für die dies `TEXTMETRIC`, `DEVMODE`, `BSTR`, und OLE-Zeichenfolgen zugeordnet. Verweisen Sie auf AFXPRIV. "H" für Weitere Informationen.  
  
## <a name="other-considerations"></a>Andere Überlegungen  
 Verwenden Sie die Makros nicht in einer dichten Schleife an. Beispielsweise möchten Sie nicht die folgende Art von Code zu schreiben:  
  
```  
void BadIterateCode(LPCTSTR lpsz)  
{  
    USES_CONVERSION; 
    for (int ii = 0; ii <10000; ii++)  
    pI->SomeMethod(ii, T2COLE(lpsz));

}  
```  
  
 Der obige Code kann dazu führen, Zuordnen von MB des Arbeitsspeichers auf dem Stapel, je nachdem welche den Inhalt der Zeichenfolge `lpsz` ist! Es verwendet auch die Zeit, um die Zeichenfolge für jede Iteration der Schleife zu konvertieren. Stattdessen verschieben Sie solche Konstanten Konvertierungen aus der Schleife:  
  
```  
void MuchBetterIterateCode(LPCTSTR lpsz)  
{  
    USES_CONVERSION; 
    LPCOLESTR lpszT = T2COLE(lpsz);

    for (int ii = 0; ii <10000; ii++)  
    pI->SomeMethod(ii, lpszT);

}  
```  
  
 Wenn die Zeichenfolge nicht konstant ist, klicken Sie dann den Aufruf der Methode in einer Funktion gekapselt werden. Dies ermöglicht die Konvertierung Puffer jedes Mal freigegeben werden. Zum Beispiel:  
  
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
  
 Geben Sie das Ergebnis eines Makros, nie zurück, es sei denn, der Rückgabewert bedeutet eine Kopie der Daten vor der Rückgabe. Dieser Code ist beispielsweise ungültig:  
  
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
  
 Der obige Code kann durch Ändern des Rückgabewerts in etwas, das den Wert kopiert behoben werden:  
  
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
  
 Die Makros sind einfach zu verwenden und einfach in den Code einfügen, aber wie Sie aus den oben genannten Einschränkungen erkennen können, müssen Sie darauf achten, dass bei ihrer Verwendung.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)


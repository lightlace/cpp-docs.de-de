---
title: "TN059: Verwenden von MFC MBCS/Unicode-Umwandlungsmakros | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.mbcs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Konvertierungsmakros [C++]"
  - "Konvertieren von Unicode"
  - "Makros [C++], MBCS-Konvertierungsmakros"
  - "MBCS [C++], Konvertierungsmakros"
  - "MFCANS32.DLL"
  - "TN059"
  - "Unicode [C++], Konvertierungsmakros"
  - "Unicode [C++], OLE-Schnittstellen"
ms.assetid: a2aab748-94d0-4e2f-8447-3bd07112a705
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# TN059: Verwenden von MFC MBCS/Unicode-Umwandlungsmakros
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert.  Daher können einige Verfahren und Themen veraltet oder falsch sein.  Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 Dieser Hinweis wird beschrieben, wie die Makros für MBCS\-\/Unicodekonvertierung verwendet, die in AFXPRIV.H. definiert werden.  Diese Makros sind besonders hilfreich, wenn die Anwendung direkt die OLE\-API oder aus irgendeinem Grund behandelt, häufig zwischen Anforderungen, Unicode und MBCS zu konvertieren.  
  
## Übersicht  
 In MFC 3.x, wurde eine besondere DLL \(MFCANS32.DLL\) verwendet um zwischen Unicode und MBCS automatisch zu konvertieren, als OLE\-Schnittstellen aufgerufen wurden.  Diese DLL war eine fast transparente Ebene, die OLE\-Anwendungen erlaubte geschrieben werden, so, als ob die OLE\-APIs und Schnittstellen von MBCS waren, obwohl sie immer Unicode sind \(außer auf Macintosh\).  Während diese Ebene bequeme und erlaubte Anwendungen war, von Win16 auf Win32 schnell portiert werden \(MFC, Microsoft Word, Microsoft Excel und VBA, sind nur einige der Microsoft\-Anwendungen, die diese Technologie haben\), hatte sie manchmal einen beträchtlichen Leistungseinbußen bei.  Aus diesem Grund verwendet MFC 4.x nicht diese DLL verweist und stattdessen direkt mit den Schnittstellen von Unicode. OLE  Um dies zu erreichen, muss MFC z Unicode verwendet MBCS konvertieren wenn eine OLE\-Schnittstelle und macht häufig mit Anforderungen zu MBCS aus Unicode konvertiert wenn eine OLE\-Schnittstelle implementiert.  Um dieses effizient und einfach behandeln einfacher zu machen, wurden mehrere Makros erstellt, diese Konvertierung.  
  
 Eine der größten Hürden des Erstellens eines solchen Satzes Makros ist Speicherbelegung.  Da die Zeichenfolgen nicht konvertiertes gesorgt sein können, muss der neue Speicherplatz, um der konvertierten Ergebnisse aufzunehmen zugeordnet werden.  Dies kann mit dem Code der Vergangenheit wurden sein, der ähnlich dem folgenden ist:  
  
```  
// we want to convert an MBCS string in lpszA  
int nLen = MultiByteToWideChar(CP_ACP, 0,lpszA, -1, NULL, NULL);  
LPWSTR lpszW = new WCHAR[nLen];  
MultiByteToWideChar(CP_ACP, 0,   
   lpszA, -1, lpszW, nLen);  
// use it to call OLE here  
pI->SomeFunctionThatNeedsUnicode(lpszW);  
// free the string  
delete[] lpszW;  
```  
  
 Dieser Ansatz als einige Probleme.  Das Hauptproblem ist, dass es viel zu schreiben ist, testen und debuggen können Code.  Einige, das ein einfacher Funktionsaufruf war, ist nun viel komplexer.  Außerdem gibt jedoch beträchtlichen Laufzeit\-Mehraufwand auf diese Weise.  Arbeitsspeicher muss auf dem Heap zugeordnet werden und freigegeben werden, wenn eine Konvertierung durchgeführt wird.  Schließlich würde der Code oben entsprechendes `#ifdefs` haben müssen, das für im Unicode\- und Macintosh\-Builds hinzugefügt wurde \(die nicht diese Konvertierung erfordern erfolgen\).  
  
 Die Projektmappe, die in aufkamen, ist, mehrere Makros erstellen, 1\) die Maske der Unterschied zwischen verschiedenen Plattformen und 2\) dem ein effizientes Speicherbelegungsschema und 3\) sind, einfach in vorhandenen Quellcode einfügen.  Im Folgenden ein Beispiel einer der Definitionen:  
  
```  
#define A2W(lpa) (\  
    ((LPCSTR)lpa == NULL) ? NULL : (\  
          _convert = (strnlen(lpa)+1),\  
        AfxA2WHelper((LPWSTR) alloca(_convert*2),   
      lpa, _convert)\  
    )\  
)  
```  
  
 Mithilfe dieses Makros anstelle von Code oben und der Punkte bedenken Sie viel einfacher:  
  
```  
// use it to call OLE here  
USES_CONVERSION;  
pI->SomeFunctionThatNeedsUnicode(T2OLE(lpszA));  
```  
  
 Es gibt zusätzliche Aufrufe, bei denen Konvertierung erforderlich ist, sondern, die Makros verwenden einfach und effektiver ist.  
  
 Die Implementierung jedes Makros verwendet die \_alloca\(\) Funktion, um vom Stapel anstelle des Heaps Speicher zu belegen.  Das Belegen vom Stapel ist wesentlich schneller als, Speicher belegend im Heap, und der Arbeitsspeicher wird automatisch freigegeben, wenn die Funktion beendet wird.  Außerdem verhindern, die Makros **MultiByteToWideChar** \(oder **WideCharToMultiByte**\) mehrfach aufrufen.  Dies geschieht, indem etwas mehr Arbeitsspeicher belegt, als notwendig ist.  Wir wissen, dass ein MBC in höchstens ein **WCHAR** konvertiert und dass für jedes **WCHAR** Sie maximal zwei MBC\-Bytes haben.  Indem etwas mehr als notwendig ausgecheckt, aber stets so, die Konvertierung zu behandeln zuordnet, wird der zweite Aufruf des Aufrufs second die Konvertierungsfunktion vermieden.  Der Aufruf der Hilfsfunktion **AfxA2Whelper** reduziert die Anzahl der Argument\-Pushs, die ausgeführt werden müssen, um die Konvertierung auszuführen \(dieser wird kleineren, als Code, wenn **MultiByteToWideChar** direkt aufgerufen wurde\).  
  
 , sodass diese die Makros Platz haben, um der temporären Länge zu speichern, ist es notwendig, eine lokale Variable zu deklarieren aufgerufen \_convert, das dies in jeder Funktion ausführt, die die Konvertierungsmakros verwendet.  Dies geschieht, indem das **USES\_CONVERSION**\-Makro aufruft, wie im Beispiel oben gezeigt.  
  
 Es gibt Konvertierungsmakros beide generischen und OLE\-Besonderen Makros.  Diese zwei verschiedenen Makrosätze werden nachfolgend erläutert.  Alle Makros befinden sich in AFXPRIV.H.  
  
## Generische Konvertierungs\-Makros  
 Die generischen Konvertierungsmakros bilden den zugrunde liegende Mechanismus.  Das Makrobeispiel und Implementierung, die im vorherigen Abschnitt, A2W angezeigt werden, ist ein solches "Generikum" Makro.  Es wird nicht zu OLE speziell verknüpft.  Der Satz generischer Makros wird unten aufgeführt:  
  
```  
A2CW      (LPCSTR) -> (LPCWSTR)  
A2W      (LPCSTR) -> (LPWSTR)  
W2CA      (LPCWSTR) -> (LPCSTR)  
W2A      (LPCWSTR) -> (LPSTR)  
```  
  
 Neben der Möglichkeit von Textkonvertierungen, gibt es zudem Makros und Hilfsfunktionen zum Konvertieren von `TEXTMETRIC`, `DEVMODE`, `BSTR` sowie der OLE zugeordneten Zeichenfolgen.  Diese Makros sind außerhalb des Umfangs dieser Diskussion \- verweisen Sie AFXPRIV.H weitere Informationen über diese Makros an.  
  
## OLE\-Konvertierungs\-Makros  
 Die OLE\-Konvertierungsmakros sind speziell für die Behandlung von Funktionen entwickelt, die **OLESTR** Zeichen erwartet.  Wenn Sie die OLE\-Kopfzeilen überprüfen, finden Sie viele Verweise auf **LPCOLESTR** und **OLECHAR**.  Diese Typen werden verwendet, um den Typ von Zeichen zu verweisen, die in OLE\-Schnittstellen auf eine Weise verwendet werden, die nicht zur Plattform bestimmt ist.  **OLECHAR** Zuordnungen zu `char` in Win16\- und Macintosh\-Plattformen und **WCHAR** in Win32.  
  
 Um die Anzahl von **\#ifdef**\-Direktive im MFC\-Code auf ein Minimum zu übergeben haben wir ein Ähnliches Makro für jede OLE\-Zeichenfolgen wo die Konvertierung einbezogen sind.  Die folgenden Makros sind das häufig verwendetste:  
  
```  
T2COLE   (LPCTSTR) -> (LPCOLESTR)  
T2OLE   (LPCTSTR) -> (LPOLESTR)  
OLE2CT   (LPCOLESTR) -> (LPCTSTR)  
OLE2T   (LPCOLESTR) -> (LPCSTR)  
```  
  
 Wiederum, gibt es ähnliche Makros für die Variante von `TEXTMETRIC`, `DEVMODE`, `BSTR` sowie der OLE zugeordneten Zeichenfolgen.  Siehe AFXPRIV.H weitere Informationen.  
  
## Andere Überlegungen  
 Verwenden Sie nicht die Makros in einer kurzen Schleife.  Beispielsweise möchten Sie die folgende Art von Code schreiben:  
  
```  
void BadIterateCode(LPCTSTR lpsz)  
{  
   USES_CONVERSION;  
   for (int ii = 0; ii < 10000; ii++)  
      pI->SomeMethod(ii, T2COLE(lpsz));  
}  
```  
  
 Der obige Code konnte führen Zuordnen von Megabyte des Speichers auf dem Stapel je nachdem, was der Inhalt der Zeichenfolge `lpsz` ist\!  Das Abschließen auch Uhrzeit, die Zeichenfolge für jede Iteration der Schleife zu konvertieren.  Stattdessen verschieben Sie solche konstanten Konvertierungen aus der Schleife:  
  
```  
void MuchBetterIterateCode(LPCTSTR lpsz)  
{  
   USES_CONVERSION;  
   LPCOLESTR lpszT = T2COLE(lpsz);  
   for (int ii = 0; ii < 10000; ii++)  
      pI->SomeMethod(ii, lpszT);  
}  
```  
  
 Wenn die Zeichenfolge nicht konstant ist, und schließen Sie den Methodenaufruf in eine Funktion.  Dies ermöglicht dem immer freigegeben werden, Konvertierungspuffer.  Beispiel:  
  
```  
void CallSomeMethod(int ii, LPCTSTR lpsz)  
{  
   USES_CONVERSION;  
   pI->SomeMethod(ii, T2COLE(lpsz));  
}  
  
void MuchBetterIterateCode2(LPCTSTR* lpszArray)  
{  
   for (int ii = 0; ii < 10000; ii++)  
      CallSomeMethod(ii, lpszArray[ii]);  
}  
```  
  
 Geben Sie nicht das Ergebnis ein der Makros zurück, vorausgesetzt, der Rückgabewert das Erstellen einer Kopie der Daten vor der Rückgabe bedeutet.  Beispielsweise ist dieser Code nicht gültig:  
  
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
  
 Der obige Code kann behoben werden, indem dem Rückgabewert zu etwas ändert, das den Wert kopiert:  
  
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
  
 Die Makros sind einfach und leicht, in den Code einzufügen, jedoch, wie Sie von den oben Vorsicht feststellen können, müssen Sie darauf achten, wenn Sie sie verwenden.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
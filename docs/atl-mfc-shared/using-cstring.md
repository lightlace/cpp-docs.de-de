---
title: Verwenden von CString | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/18/2018
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CString objects, C++ string manipulation
- CString objects, reference counting
- CString class (Visual C++)
ms.assetid: ed018aaf-8b10-46f9-828c-f9c092dc7609
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e3de9b373a80ef939f5ac5ff3d746e0ebdc8b74
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405462"
---
# <a name="using-cstring"></a>Verwenden von CString

In den Themen in diesem Abschnitt wird die Programmierung mit `CString` beschrieben. Referenzdokumentation zu den `CString` Klasse, finden Sie in der Dokumentation für [CStringT](../atl-mfc-shared/reference/cstringt-class.md).

Schließen Sie zum Verwenden von `CString` den `atlstr.h`-Header ein.

Die `CString`, `CStringA`, und `CStringW` -Klassen sind spezialisierungen einer Klassenvorlage namens [CStringT](../atl-mfc-shared/reference/cstringt-class.md) basierend auf dem Typ von Zeichendaten, die sie unterstützen.

Ein `CStringW` Objekt enthält die **"wchar_t"** -Typ und unterstützt Unicode-Zeichenfolgen. Ein `CStringA` Objekt enthält die **Char** Typ und der Zeichenfolgen für die Einzelbyte- und Multibyte (MBCS) unterstützt. Ein `CString` -Objekt unterstützt die **Char** Typ oder die `wchar_t` Typ, je nachdem, ob das Symbol für MBCS oder Unicode-Zeichen zum Zeitpunkt der Kompilierung definiert ist.

Ein `CString`-Objekt hält Zeichendaten in einem `CStringData`-Objekt. `CString` lässt NULL-terminierte c-Zeichenfolgen. `CString` verfolgt die Zeichenfolge Länge für höhere Leistung, sondern auch behält den NULL-Zeichen in den gespeicherten Zeichendaten zur Unterstützung der Konvertierung in LPCWSTR. `CString` enthält den null-Terminator an, wenn es sich um eine Zeichenfolge im C-Format exportiert. Sie können einen NULL-Wert einfügen, an anderen Speicherorten in ein `CString`, aber es kann zu unerwarteten Ergebnissen führen.

Der folgende Satz an Zeichenfolgenklassen kann ohne Verknüpfung einer MFC-Bibliothek mit oder ohne CRT-Support verwendet werden: `CAtlString`, `CAtlStringA`, und `CAtlStringW`.

`CString` wird in nativen Projekten verwendet werden. Verwenden Sie für Projekte mit verwaltetem Code (C++/CLI) `System::String`.

Um mehr Funktionen hinzuzufügen als `CString`, `CStringA` oder `CStringW` derzeit bieten, sollten Sie eine Unterklasse von `CStringT` erstellen, die die zusätzlichen Funktionen enthält.

Der folgende Code zeigt, wie Sie einen `CString` erstellen und als Standardausgabe drucken können:

```cpp  
#include <atlstr.h>

int main() {  
    CString aCString = CString(_T("A string"));  
    _tprintf(_T("%s"), (LPCTSTR) aCString);  
}  
```

## <a name="in-this-section"></a>In diesem Abschnitt

[Grundlegende CString-Operationen](../atl-mfc-shared/basic-cstring-operations.md)<br/>
Beschreibt grundlegende `CString`-Vorgänge, darunter das Erstellen von Objekten aus C-Literal-Zeichenfolgen, das Zugreifen auf einzelne Zeichen in einem `CString`, das Verketten von zwei Objekten und das Vergleichen von `CString`-Objekten.

[Zeichenfolgendatenverwaltung](../atl-mfc-shared/string-data-management.md)<br/>
Erläutert die Nutzung von Unicode und MBCS mit `CString`.

[CString-Semantik](../atl-mfc-shared/cstring-semantics.md)<br/>
Erläutert, wie `CString`-Objekte verwendet werden.

[CString-Operationen bei Zeichenfolgen im C-Format](../atl-mfc-shared/cstring-operations-relating-to-c-style-strings.md)<br/>
Beschreibt die Manipulation der Inhalte eines `CString`-Objekts wie eine mit Null abschließende Zeichenfolge im C-Format.

[Zuweisen und Freigeben von Arbeitsspeicher für einen BSTR](../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md)<br/>
Erläutert die Verwendung von Arbeitsspeicher für einen BSTR und COM-Objekte.

[CString-Ausnahmebereinigung](../atl-mfc-shared/cstring-exception-cleanup.md)<br/>
Erklärt, dass eine explizite Bereinigung in MFC 3.0 und höher nicht mehr notwendig ist.

[CString-Argumentübergabe](../atl-mfc-shared/cstring-argument-passing.md)<br/>
Erläutert, wie Sie CString-Objekte an Funktionen übergeben und wie Sie `CString`-Objekte aus Funktionen zurückgeben können.

[Unterstützung für Unicode- und Multibyte-Zeichensätze (MBCS)](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)<br/>
Beschreibt, wie MFC für Unicode- und MBCS-Unterstützung aktiviert wird.

## <a name="reference"></a>Referenz

[CStringT](../atl-mfc-shared/reference/cstringt-class.md)<br/>
Bietet Referenzinformationen zur `CStringT`-Klasse.

[CSimpleStringT-Klasse](../atl-mfc-shared/reference/csimplestringt-class.md)<br/>
Bietet Referenzinformationen zur `CSimpleStringT`-Klasse.

## <a name="related-sections"></a>Verwandte Abschnitte

[Zeichenfolgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
Enthält Links zu Themen, in denen verschiedene Methoden zum Verwalten von Zeichenfolgendaten beschrieben werden.

[Zeichenfolgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)


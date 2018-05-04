---
title: Verwenden von CString | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 591a319671ea42236af5ae7e80ea1cb94c3c446c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="using-cstring"></a>Verwenden von CString
In den Themen in diesem Abschnitt wird die Programmierung mit `CString` beschrieben. Referenzdokumentation zu den `CString` -Klasse finden Sie in der Dokumentation für [CStringT](../atl-mfc-shared/reference/cstringt-class.md).  
  
 Schließen Sie zum Verwenden von `CString` den `atlstr.h`-Header ein.  
  
 Die `CString`, `CStringA`, und `CStringW` -Klassen sind spezialisierungen einer Klassenvorlage namens [CStringT](../atl-mfc-shared/reference/cstringt-class.md) basierend auf dem Typ von Zeichendaten, die sie unterstützen.  
  
 Ein `CStringW`-Objekt enthält den `wchar_t`-Typ und unterstützt Unicode-Zeichenfolgen. Ein `CStringA`-Objekt enthält den `char`-Typ und unterstützt Singlebyte- und Multibyte (MBCS)-Zeichenfolgen. Ein `CString`-Objekt unterstützt den `char`-Typ oder den `wchar_t`-Typ, je nachdem, ob das `MBCS`-Symbol oder das `UNICODE`-Symbol bei der Kompilierung definiert wurde.  
  
 Ein `CString`-Objekt hält Zeichendaten in einem `CStringData`-Objekt. `CString` akzeptiert `null`-beendete C-Stil Zeichenfolgen, jedoch wird keine beibehalten der `null` Zeichen in die gespeicherte Zeichendaten. Stattdessen verfolgt `CString` die Zeichenfolgenlänge. `CString` bietet ein null-Abschlusszeichen, wenn es sich um eine Zeichenfolge im C-Format exportiert. Sie können eine `null` in einen `CString` einfügen, dies kann jedoch zu unerwarteten Ergebnissen führen.  
  
 Die folgende Gruppe von Klassen kann verwendet werden, ohne zu verknüpfen eine MFC-Bibliothek mit oder ohne CRT-Unterstützung: `CAtlString`, `CAtlStringA`, und `CAtlStringW`.  
  
 `CString` wird in systemeigene Projekte verwendet. Verwenden Sie für Projekte mit verwaltetem Code (C++/CLI) `System::String`.  
  
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
 [Grundlegende CString-Operationen](../atl-mfc-shared/basic-cstring-operations.md)  
 Beschreibt grundlegende `CString`-Vorgänge, darunter das Erstellen von Objekten aus C-Literal-Zeichenfolgen, das Zugreifen auf einzelne Zeichen in einem `CString`, das Verketten von zwei Objekten und das Vergleichen von `CString`-Objekten.  
  
 [Zeichenfolgendatenverwaltung](../atl-mfc-shared/string-data-management.md)  
 Erläutert die Nutzung von Unicode und MBCS mit `CString`.  
  
 [CString-Semantik](../atl-mfc-shared/cstring-semantics.md)  
 Erläutert, wie `CString`-Objekte verwendet werden.  
  
 [CString-Operationen bei Zeichenfolgen im C-Format](../atl-mfc-shared/cstring-operations-relating-to-c-style-strings.md)  
 Beschreibt die Manipulation der Inhalte eines `CString`-Objekts wie eine mit Null abschließende Zeichenfolge im C-Format.  
  
 [Zuweisen und Freigeben von Arbeitsspeicher für einen BSTR](../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md)  
 Erläutert die Nutzung von Arbeitsspeicher für einen `BSTR` und für COM-Objekte.  
  
 [CString-Ausnahmebereinigung](../atl-mfc-shared/cstring-exception-cleanup.md)  
 Erklärt, dass eine explizite Bereinigung in MFC 3.0 und höher nicht mehr notwendig ist.  
  
 [CString-Argumentübergabe](../atl-mfc-shared/cstring-argument-passing.md)  
 Erläutert, wie Sie CString-Objekte an Funktionen übergeben und wie Sie `CString`-Objekte aus Funktionen zurückgeben können.  
  
 [Unterstützung für Unicode- und Multibyte-Zeichensätze (MBCS)](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)  
 Beschreibt, wie MFC für Unicode- und MBCS-Unterstützung aktiviert wird.  
  
## <a name="reference"></a>Referenz  
 [CStringT](../atl-mfc-shared/reference/cstringt-class.md)  
 Bietet Referenzinformationen zur `CStringT`-Klasse.  
  
 [CSimpleStringT-Klasse](../atl-mfc-shared/reference/csimplestringt-class.md)  
 Bietet Referenzinformationen zur `CSimpleStringT`-Klasse.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Zeichenfolgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)  
 Enthält Links zu Themen, in denen verschiedene Methoden zum Verwalten von Zeichenfolgendaten beschrieben werden.  
  
 [Zeichenfolgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)


---
title: "Using CString"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CString class (Visual C++)"
  - "CString objects, C++ string manipulation"
  - "CString objects, reference counting"
ms.assetid: ed018aaf-8b10-46f9-828c-f9c092dc7609
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Using CString
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In den Themen in diesem Abschnitt wird die Programmierung mit `CString` beschrieben.  Referenzdokumentation über die `CString`\-Klasse finden Sie in der Dokumentation für [CStringT](../atl-mfc-shared/reference/cstringt-class.md).  
  
 Schließen Sie zum Verwenden von `CString` den `atlstr.h`\-Header ein.  
  
 Die `CString`\-, `CStringA`\- und `CStringW`\-Klassen sind Spezialisierungen einer Klassenvorlage namens [CStringT](../atl-mfc-shared/reference/cstringt-class.md), basierend auf dem Typ der unterstützten Zeichendaten.  
  
 Ein `CStringW`\-Objekt enthält den `wchar_t`\-Typ und unterstützt Unicode\-Zeichenfolgen.  Ein `CStringA`\-Objekt enthält den `char`\-Typ und unterstützt Singlebyte\- und Multibyte \(MBCS\)\-Zeichenfolgen.  Ein `CString`\-Objekt unterstützt den `char`\-Typ oder den `wchar_t`\-Typ, je nachdem, ob das `MBCS`\-Symbol oder das `UNICODE`\-Symbol bei der Kompilierung definiert wurde.  
  
 Ein `CString`\-Objekt hält Zeichendaten in einem `CStringData`\-Objekt.  `CString` akzeptiert mit `null` abschließende Zeichenfolgen im C\-Format, bewahrt jedoch nicht das `null`\-Zeichen in den gespeicherten Zeichendaten.  Stattdessen verfolgt `CString` die Zeichenfolgenlänge.  `CString` bietet ein Null\-Abschlusszeichen, wenn eine Zeichenfolge im C\-Format exportiert wird.  Sie können eine `null` in einen `CString` einfügen, dies kann jedoch zu unerwarteten Ergebnissen führen.  
  
 Der folgende Satz an Zeichenfolgenklassen kann ohne Verknüpfung einer MFC\-Bibliothek mit oder ohne CRT\-Support verwendet werden: `CAtlString`, `CAtlStringA` und `CAtlStringW`.  
  
 `CString` wird in nativen Projekten verwendet.  Verwenden Sie für Projekte mit verwaltetem Code \(C\+\+\/CLI\) `System::String`.  
  
 Um mehr Funktionen hinzuzufügen als `CString`, `CStringA` oder `CStringW` derzeit bieten, sollten Sie eine Unterklasse von `CStringT` erstellen, die die zusätzlichen Funktionen enthält.  
  
 Der folgende Code zeigt, wie Sie einen `CString` erstellen und als Standardausgabe drucken können:  
  
```cpp  
#include <atlstr.h>  
  
int main() {  
    CString aCString = CString(_T("A string"));  
    _tprintf(_T("%s"), (LPCTSTR) aCString);  
}  
```  
  
## In diesem Abschnitt  
 [Grundlegende CString\-Vorgänge](../atl-mfc-shared/basic-cstring-operations.md)  
 Beschreibt grundlegende `CString`\-Vorgänge, darunter das Erstellen von Objekten aus C\-Literal\-Zeichenfolgen, das Zugreifen auf einzelne Zeichen in einem `CString`, das Verketten von zwei Objekten und das Vergleichen von `CString`\-Objekten.  
  
 [Zeichenfolgendatenverwaltung](../atl-mfc-shared/string-data-management.md)  
 Erläutert die Nutzung von Unicode und MBCS mit `CString`.  
  
 [CString\-Semantik](../atl-mfc-shared/cstring-semantics.md)  
 Erläutert, wie `CString`\-Objekte verwendet werden.  
  
 [CString\-Vorgänge bei Zeichenfolgen im C\-Format](../atl-mfc-shared/cstring-operations-relating-to-c-style-strings.md)  
 Beschreibt die Manipulation der Inhalte eines `CString`\-Objekts wie eine mit Null abschließende Zeichenfolge im C\-Format.  
  
 [Zuweisen und Freigeben von Arbeitsspeicher für einen BSTR](../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md)  
 Erläutert die Nutzung von Arbeitsspeicher für einen `BSTR` und für COM\-Objekte.  
  
 [CString\-Ausnahmebereinigung](../atl-mfc-shared/cstring-exception-cleanup.md)  
 Erklärt, dass eine explizite Bereinigung in MFC 3.0 und höher nicht mehr notwendig ist.  
  
 [CString\-Argumentenübergabe](../atl-mfc-shared/cstring-argument-passing.md)  
 Erläutert, wie Sie CString\-Objekte an Funktionen übergeben und wie Sie `CString`\-Objekte aus Funktionen zurückgeben können.  
  
 [Unterstützung für Unicode\- und Multibyte\-Zeichensätze \(MBCS\)](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)  
 Beschreibt, wie MFC für Unicode\- und MBCS\-Unterstützung aktiviert wird.  
  
## Referenz  
 [CStringT](../atl-mfc-shared/reference/cstringt-class.md)  
 Bietet Referenzinformationen zur `CStringT`\-Klasse.  
  
 [CSimpleStringT Class](../atl-mfc-shared/reference/csimplestringt-class.md)  
 Bietet Referenzinformationen zur `CSimpleStringT`\-Klasse.  
  
## Verwandte Abschnitte  
 [Zeichenfolgen](../atl-mfc-shared/strings-atl-mfc.md)  
 Enthält Links zu Themen, in denen verschiedene Methoden zum Verwalten von Zeichenfolgendaten beschrieben werden.  
  
 [Klassenvorlageninstanziierung](../Topic/Class%20Template%20Instantiation.md)  
 `CString` ist eine `typedef`, basierend auf `CStringT`, einer Instanz einer Spezialisierung einer Klassenvorlage.
---
title: Grundlegende CString-Vorgänge | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CString objects, basic operations
- string literals, CString operations
- literal strings, CString operations
- CString objects
- string comparison, CString operations
- characters, accessing in CStrings
ms.assetid: 41db66b2-9427-4bb3-845a-9b6869159a6c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b66b6fc5578960e4b6ec9b392622256b66db9cfa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="basic-cstring-operations"></a>Grundlegende CString-Vorgänge
In diesem Thema wird erläutert, die folgende einfache [CString](../atl-mfc-shared/reference/cstringt-class.md) Vorgänge:  
  
- [CString-Objekte erstellen, von standard-C-Literalzeichenfolgen](#_core_creating_cstring_objects_from_standard_c_literal_strings)  
  
- [Zugreifen auf einzelne Zeichen in CString](#_core_accessing_individual_characters_in_a_cstring)  
  
- [Verketten von zwei CString-Objekte](#_core_concatenating_two_cstring_objects)  
  
- [Vergleichen von CString-Objekte](#_core_comparing_cstring_objects)  
  
- [Konvertieren von CString-Objekte](#_core_converting_cstring_objects)  
  
 `Class CString` basiert auf der Klassenvorlage [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md). `CString` ist eine `typedef` von `CStringT`. Mehr genau `CString` ist ein `typedef` von einer *explizite Spezialisierung* von `CStringT`, dies ist eine allgemeine Möglichkeit, eine Klassenvorlage zu verwenden, um eine Klasse zu definieren. Auf ähnliche Weise definierte Klassen sind `CStringA` und `CStringW`.  
  
 `CString`, `CStringA`, und `CStringW` in atlstr.h definiert sind. `CStringT` wird in cstringt.h definiert.  
  
 `CString`, `CStringA`, und `CStringW` jeweils einen Satz von Methoden und definierten Operatoren abrufen `CStringT` für die Verwendung mit der Zeichenfolgendaten, die sie unterstützen. Einige der Methoden doppelte und in einigen Fällen (warningthreshold) überschreiten die Zeichenfolge-Dienste von der C-Laufzeitbibliotheken.  
  
 Hinweis: `CString` ist eine systemeigene Klasse. Für eine Klasse, die für die Verwendung in einem C++ ist c++ / CLI verwaltet Projekt verwenden `System.String`.  
  
##  <a name="_core_creating_cstring_objects_from_standard_c_literal_strings"></a> CString-Objekte erstellen, von Standard-C-Zeichenfolgenliterale  
 Können Sie die C-Stil Literalzeichenfolgen zum Zuweisen einer `CString` so fest, wie Sie eine zuweisen können `CString` zu einem anderen Objekt.  
  
-   Weisen Sie den Wert einer Literalzeichenfolge "C" zu einem `CString` Objekt.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#183](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_1.cpp)]  
  
-   Weisen Sie den Wert eines `CString` in eine andere `CString` Objekt.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#184](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_2.cpp)]  
  
     Der Inhalt des eine `CString` Objekt werden kopiert, wenn bei mindestens einer `CString` zu einem anderen-Objekt zugewiesen ist. Aus diesem Grund freigeben werden die beiden Zeichenfolgen keinen Verweis auf die tatsächlichen Zeichen, die die Zeichenfolge bilden. Weitere Informationen zur Verwendung von `CString` Objekte als Werte finden Sie unter [CString-Semantik](../atl-mfc-shared/cstring-semantics.md).  
  
    > [!NOTE]
    >  Zum Schreiben der Anwendung, sodass es für Unicode oder ANSI, codieren Sie Zeichenfolgenliterale mit dem _T-Makro kompiliert werden kann. Weitere Informationen finden Sie unter [Unicode- und Multibyte-Zeichensätzen (MBCS)-Unterstützung](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).  
  
##  <a name="_core_accessing_individual_characters_in_a_cstring"></a> Zugreifen auf einzelne Zeichen in CString  
 Sie erreichen die einzelne Zeichen in einer `CString` Objekt mithilfe der `GetAt` und `SetAt` Methoden. Sie können auch den Array-Element oder Feldindex,-Operator ([]) anstelle von `GetAt` zum Abrufen der einzelner Zeichen. (Dies ähnelt den Zugriff auf Arrayelemente über einen Index, wie in der standard-c-Zeichenfolgen.) Indizieren Sie die Werte für `CString` Zeichen sind nullbasiert.  
  
##  <a name="_core_concatenating_two_cstring_objects"></a> Verketten von zwei CString-Objekte  
 Zum Verketten von zwei `CString` Objekte, verwenden Sie die Verkettungsoperatoren (+ oder +=) wie folgt.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#185](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_3.cpp)]  
  
 Mindestens ein Argument an die Verkettungsoperatoren (+ oder +=) muss eine `CString` -Objekt, aber Sie können eine Konstante Zeichenfolge verwenden (z. B. `"big"`) oder eine `char` (z. B. "X") für das andere Argument.  
  
##  <a name="_core_comparing_cstring_objects"></a> Vergleichen von CString-Objekte  
 Die `Compare` Methode und den Operator ==-Operator für `CString` sind gleichwertig. `Compare`, `operator==`, und `CompareNoCase` werden MBCS und Unicode-fähig; `CompareNoCase` ist auch in der Groß-/Kleinschreibung. Die `Collate` Methode `CString` gebietsschemabezogene und häufig langsamer als `Compare`. Verwendung `Collate` gemäß Regeln nur, in dem Sie die Sortierung zustimmen müssen, die durch das aktuelle Gebietsschema.  
  
 Die folgende Tabelle zeigt die verfügbaren [CString](../atl-mfc-shared/reference/cstringt-class.md) Vergleichsfunktionen und die entsprechenden Unicode/MBCS-Portable-Funktionen in der C-Laufzeitbibliothek.  
  
|CString-Funktion|MBCS-Funktion|Unicode-Funktion|  
|----------------------|-------------------|----------------------|  
|`Compare`|`_mbscmp`|`wcscmp`|  
|`CompareNoCase`|`_mbsicmp`|`_wcsicmp`|  
|`Collate`|`_mbscoll`|`wcscoll`|  
  
 Die `CStringT` Klassenvorlage definiert die relationalen Operatoren (<, \<=, > =, >, == und! =), stehen für die Verwendung durch `CString`. Sie können zwei vergleichen `CStrings` mithilfe dieser Operatoren, wie im folgenden Beispiel gezeigt.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#186](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_4.cpp)]  
  
##  <a name="_core_converting_cstring_objects"></a> Konvertieren von CString-Objekte  
 Informationen zum Konvertieren von CString-Objekten in andere Zeichenfolgen-Datentypen finden Sie unter [wie: Konvertieren zwischen verschiedenen Zeichenfolgentypen](../text/how-to-convert-between-various-string-types.md).  
  
## <a name="using-cstring-with-wcout"></a>Verwenden von CString mit wcout  
 Verwenden ein CString-Objekts mit `wcout` müssen Sie explizit das Objekt, das Umwandeln einer `const wchar_t*` wie im folgenden Beispiel gezeigt:  
  
```  
CString cs("meow");

    wcout <<(const wchar_t*) cs <<endl;  
 
```  
  
 Ohne die Umwandlung `cs` so behandelt, als eine `void*` und `wcout` gibt die Adresse des Objekts. Dieses Verhalten wird verursacht, indem feine Interaktionen zwischen Argument Abzug und Überladung vorlagenauflösung die eigenen richtig sind und den geschäftsanforderungen entsprechen, mit der C++-Standard.  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [CStringT-Klasse](../atl-mfc-shared/reference/cstringt-class.md)   
 [Spezialisierung einer Klassenvorlage](../cpp/template-specialization-cpp.md)   
 [Vorgehensweise: Konvertieren zwischen verschiedenen Zeichenfolgentypen](../text/how-to-convert-between-various-string-types.md)


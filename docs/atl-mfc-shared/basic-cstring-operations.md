---
title: Grundlegende CString-Vorgänge
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, basic operations
- string literals, CString operations
- literal strings, CString operations
- CString objects
- string comparison, CString operations
- characters, accessing in CStrings
ms.assetid: 41db66b2-9427-4bb3-845a-9b6869159a6c
ms.openlocfilehash: d1f16e470123bd52cb2656541aafaabdfc16af8c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434074"
---
# <a name="basic-cstring-operations"></a>Grundlegende CString-Vorgänge

In diesem Thema wird erläutert, die folgende einfache [CString](../atl-mfc-shared/reference/cstringt-class.md) Vorgänge:

- [Erstellen von CString-Objekte aus standard C-Zeichenfolgenliterale](#_core_creating_cstring_objects_from_standard_c_literal_strings)

- [Zugreifen auf einzelne Zeichen in ein CString](#_core_accessing_individual_characters_in_a_cstring)

- [Verketten von zwei CString-Objekten](#_core_concatenating_two_cstring_objects)

- [Vergleichen von CString-Objekten](#_core_comparing_cstring_objects)

- [Konvertieren von CString-Objekten](#_core_converting_cstring_objects)

`Class CString` basiert auf der Klassenvorlage [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md). `CString` ist eine **Typedef** von `CStringT`. Genauer gesagt werden `CString` ist eine **Typedef** von einer *explizite Spezialisierung* von `CStringT`, dies ist eine allgemeine Möglichkeit zum eine Klassenvorlage zu verwenden, um eine Klasse zu definieren. Auf ähnliche Weise definierte Klassen sind `CStringA` und `CStringW`.

`CString`, `CStringA`, und `CStringW` in atlstr.h definiert sind. `CStringT` wird in cstringt.h definiert.

`CString`, `CStringA`, und `CStringW` jeweils einen Satz von Methoden und definierten Operatoren abrufen `CStringT` für die Verwendung mit der Zeichenfolgendaten, die sie unterstützen. Einige der Methoden doppelte und in einigen Fällen (warningthreshold) überschreiten die Zeichenfolge-Dienste, von der C-Laufzeitbibliotheken.

Hinweis: `CString` ist eine systemeigene Klasse. Für eine Klasse, die für die Verwendung in einem C++ / CLI verwalteten Projekt verwenden `System.String`.

##  <a name="_core_creating_cstring_objects_from_standard_c_literal_strings"></a> CString-Objekte erstellen, von Standard-C-Zeichenfolgenliterale

Sie können literale Zeichenfolgen im C-Stil zuweisen eine `CString` genauso wie Sie eine zuweisen können `CString` Objekt in einen anderen.

- Weisen Sie den Wert einer C-Literalzeichenfolge, einen `CString` Objekt.

   [!code-cpp[NVC_ATLMFC_Utilities#183](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_1.cpp)]

- Weisen Sie den Wert eines `CString` in ein anderes `CString` Objekt.

   [!code-cpp[NVC_ATLMFC_Utilities#184](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_2.cpp)]

   Den Inhalt einer `CString` Objekt kopiert werden, wenn bei mindestens einer `CString` zu einem anderen-Objekt zugewiesen ist. Aus diesem Grund weisen die beiden Zeichenfolgen einen Verweis auf die tatsächlichen Zeichen nicht, die die Zeichenfolge bilden. Weitere Informationen zur Verwendung von `CString` Objekte als Werte finden Sie unter [CString-Semantik](../atl-mfc-shared/cstring-semantics.md).

   > [!NOTE]
   > Um Ihre Anwendung zu schreiben, damit er für Unicode oder ANSI, codieren Sie Zeichenfolgenliterale mit dem _T-Makro kompiliert werden kann. Weitere Informationen finden Sie unter [Unicode- und Multibyte-Zeichensatz (MBCS) Unterstützung](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).

##  <a name="_core_accessing_individual_characters_in_a_cstring"></a> Zugreifen auf einzelne Zeichen in ein CString

Es stehen einzelne Zeichen in einem `CString` -Objekt unter Verwendung der `GetAt` und `SetAt` Methoden. Sie können auch die Array-Elements oder Index,-Operator ([]) anstelle von `GetAt` um einzelne Zeichen zu erhalten. (Dies ähnelt den Zugriff auf Elemente des Arrays anhand des Indexes, wie im standard-c-Zeichenfolgen an.) Indizieren Sie Werte für `CString` Zeichen sind nullbasiert.

##  <a name="_core_concatenating_two_cstring_objects"></a> Verketten von zwei CString-Objekten

Zum Verketten von zwei `CString` Objekte zu verwenden, die Verkettungsoperatoren (+ oder +=) wie folgt.

[!code-cpp[NVC_ATLMFC_Utilities#185](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_3.cpp)]

Mindestens ein Argument für die Operatoren für das Verketten (+ oder +=) muss eine `CString` -Objekt, aber Sie können eine Konstante Zeichenfolge verwenden (z. B. `"big"`) oder ein **Char** (z. B. "X") für das andere Argument.

##  <a name="_core_comparing_cstring_objects"></a> Vergleichen von CString-Objekten

Die `Compare` Methode und den Operator ==-Operator für `CString` entsprechen. `Compare`, **Operator ==**, und `CompareNoCase` kennen MBCS und Unicode; `CompareNoCase` ist auch in der Groß-/Kleinschreibung. Die `Collate` -Methode der `CString` gebietsschemabezogene und häufig langsamer als `Compare`. Verwendung `Collate` gemäß Regeln nur, in dem Sie durch die Sortierung befolgt werden müssen, die vom aktuellen Gebietsschema.

Die folgende Tabelle zeigt die verfügbaren [CString](../atl-mfc-shared/reference/cstringt-class.md) Vergleichsfunktionen und die entsprechenden Unicode/MBCS-Portable-Funktionen in der C-Laufzeitbibliothek.

|CString-Funktion|MBCS-Funktion|Unicode-Funktion|
|----------------------|-------------------|----------------------|
|`Compare`|`_mbscmp`|`wcscmp`|
|`CompareNoCase`|`_mbsicmp`|`_wcsicmp`|
|`Collate`|`_mbscoll`|`wcscoll`|

Die `CStringT` -Klassenvorlage definiert die relationalen Operatoren (<, \<=, > =, >, ==, und! =), die für die Verwendung durch verfügbar sind `CString`. Sie können vergleichen zwei `CStrings` mithilfe dieser Operatoren, wie im folgenden Beispiel gezeigt.

[!code-cpp[NVC_ATLMFC_Utilities#186](../atl-mfc-shared/codesnippet/cpp/basic-cstring-operations_4.cpp)]

##  <a name="_core_converting_cstring_objects"></a> Konvertieren von CString-Objekten

Informationen zum Konvertieren von CString-Objekte in anderen Zeichenfolgentypen finden Sie unter [wie: Konvertieren zwischen verschiedenen Zeichenfolgentypen](../text/how-to-convert-between-various-string-types.md).

## <a name="using-cstring-with-wcout"></a>Verwenden von CString mit wcout

Verwenden ein CString-Objekts mit `wcout` müssen Sie das Objekt, das explizit Umwandeln einer `const wchar_t*` wie im folgenden Beispiel gezeigt:

```
CString cs("meow");

    wcout <<(const wchar_t*) cs <<endl;

```

Ohne diese Umwandlung `cs` behandelt, als eine `void*` und `wcout` gibt die Adresse des Objekts aus. Dieses Verhalten wird verursacht durch geringfügige Interaktionen zwischen Argument Abzug und Überladung vorlagenauflösung in sich selbst richtig sind und konform mit der C++-Standard.

## <a name="see-also"></a>Siehe auch

[Zeichenfolgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CStringT-Klasse](../atl-mfc-shared/reference/cstringt-class.md)<br/>
[Vorlagenspezialisierung](../cpp/template-specialization-cpp.md)<br/>
[Vorgehensweise: Konvertieren zwischen verschiedenen Zeichenfolgentypen](../text/how-to-convert-between-various-string-types.md)


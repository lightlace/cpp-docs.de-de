---
title: Eingabe-/Ausgabestreams
ms.date: 11/04/2016
helpviewer_keywords:
- I/O [C++], stream
- stream I/O
ms.assetid: 21a97566-91a7-42d6-b2f8-a4c16bc926f1
ms.openlocfilehash: 3d5344ede3a62375c4c8102d1fc39445518eb0c4
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455269"
---
# <a name="inputoutput-streams"></a>Eingabe-/Ausgabestreams

`basic_iostream`, welches in der Headerdatei \<istream > definiert ist, ist die Klassenvorlage für Objekte, die zeichenbasierte Ein- und Ausgabe-E/A-Streams behandeln.

Es gibt zwei Typdefinitionen, die zeichenspezifische Spezialisierungen von `basic_iostream` definieren und helfen können, den Code leichter lesbar zu machen: `iostream` (nicht zu verwechseln mit der Headerdatei \<iostream >) ist ein E/A-Stream, der auf `basic_iostream<char>` basiert; `wiostream` ist ein E/A-Stream, der auf `basic_iostream<wchar_t>` basiert.

Weitere Informationen finden Sie unter [basic_iostream-Klasse](../standard-library/basic-iostream-class.md), [iostream](../standard-library/basic-iostream-class.md), und [wiostream](../standard-library/basic-iostream-class.md).

Abgeleitet von `basic_iostream` ist die Klassenvorlage `basic_fstream`, die zum Übertragen von Zeichendaten in und aus Dateien verwendet wird.

Es gibt auch Typdefinitionen, die zeichenspezifische Spezialisierungen von `basic_fstream` bereitstellen. Dabei handelt es sich um einen Datei-e/a-Stream, der auf **char**basiert `wfstream`, und, bei dem es sich um einen Datei-e/a-Stream handelt, der auf wchar_t basiert.  `fstream` Weitere Informationen finden Sie unter [basic_fstream-Klasse](../standard-library/basic-fstream-class.md), [fstream](../standard-library/basic-fstream-class.md) und [wfstream](../standard-library/basic-fstream-class.md). Die Verwendung dieser Typdefinitionen benötigt die Aufnahme der Headerdatei \<fstream >.

> [!NOTE]
> Wenn ein `basic_fstream`-Objekt die Datei-E/A verwendet, obwohl die zugrundeliegenden Puffer separat festgelegte Positionen für Lesen und Schreiben enthalten, sind die aktuellen Eingabe- und Ausgabepositionen miteinander verbunden. Das Lesen einiger Daten verschiebt die Ausgabeposition.

Die Klassenvorlage `basic_stringstream` und seine allgemeine Spezialisierung `stringstream`, werden häufig zum Arbeiten mit E/A-Streamobjekten zum Einfügen und Extrahieren von Zeichendaten verwendet. Weitere Informationen finden Sie unter [basic_stringstream-Klasse](../standard-library/basic-stringstream-class.md).

## <a name="see-also"></a>Siehe auch

[stringstream](../standard-library/basic-stringstream-class.md)\
[basic_stringstream-Klasse](../standard-library/basic-stringstream-class.md)\
[\<sstream>](../standard-library/sstream.md)\
[iostream-Programmierung](../standard-library/iostream-programming.md)\
[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)

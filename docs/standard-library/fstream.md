---
title: '&lt;fstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <fstream>
helpviewer_keywords:
- fstream header
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
ms.openlocfilehash: ba6a4152b8d37f5b0186f9d05c6ba850e8c2e54c
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454021"
---
# <a name="ltfstreamgt"></a>&lt;fstream&gt;

Definiert mehrere Klassen, die iostreams-Vorgänge für Sequenzen unterstützen, die in externen Dateien gespeichert sind.

## <a name="syntax"></a>Syntax

```cpp
#include <fstream>
```

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[filebuf](../standard-library/fstream-typedefs.md#filebuf)|Ein Typ `basic_filebuf` , der auf **char** -Vorlagen Parameter spezialisiert ist.|
|[fstream](../standard-library/fstream-typedefs.md#fstream)|Ein Typ `basic_fstream` , der auf **char** -Vorlagen Parameter spezialisiert ist.|
|[ifstream](../standard-library/fstream-typedefs.md#ifstream)|Ein Typ `basic_ifstream` , der auf **char** -Vorlagen Parameter spezialisiert ist.|
|[ofstream](../standard-library/fstream-typedefs.md#ofstream)|Ein Typ `basic_ofstream` , der auf **char** -Vorlagen Parameter spezialisiert ist.|
|[wfstream](../standard-library/fstream-typedefs.md#wfstream)|Ein Typ `basic_fstream` , der auf **wchar_t** -Vorlagen Parameter spezialisiert ist.|
|[wifstream](../standard-library/fstream-typedefs.md#wifstream)|Ein Typ `basic_ifstream` , der auf **wchar_t** -Vorlagen Parameter spezialisiert ist.|
|[wofstream](../standard-library/fstream-typedefs.md#wofstream)|Ein Typ `basic_ofstream` , der auf **wchar_t** -Vorlagen Parameter spezialisiert ist.|
|[wfilebuf](../standard-library/fstream-typedefs.md#wfilebuf)|Ein Typ `basic_filebuf` , der auf **wchar_t** -Vorlagen Parameter spezialisiert ist.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[basic_filebuf](../standard-library/basic-filebuf-class.md)|Die Vorlagenklasse beschreibt einen die Übertragung zu und aus einer Sequenz von in einer externen Datei gespeicherten Elementen von Elementen des Typs `Elem` steuernden Streampuffer, dessen Zeichenmerkmale durch die Klasse `Tr` ermittelt werden.|
|[basic_fstream](../standard-library/basic-fstream-class.md)|Die Vorlagen Klasse beschreibt ein Objekt, das das Einfügen und Extrahieren von Elementen und codierten Objekten mit einem Streampuffer der Klasse [Basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **TR**> mit Elementen des `Elem`Typs steuert, dessen Zeichen Merkmale werden von der-Klasse `Tr`bestimmt.|
|[basic_ifstream](../standard-library/basic-ifstream-class.md)|Die Vorlagen Klasse beschreibt ein Objekt, das das Extrahieren von Elementen und codierten Objekten aus einem Streampuffer der Klasse [Basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **TR**> mit Elementen des `Elem`Typs steuert, dessen Zeichen Merkmale werden von der-Klasse `Tr`bestimmt.|
|[basic_ofstream](../standard-library/basic-ofstream-class.md)|Die Vorlagen Klasse beschreibt ein Objekt, das das Einfügen von Elementen und codierten Objekten in einen Streampuffer der Klasse [Basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **TR**> mit Elementen des `Elem`Typs steuert, dessen Zeichen Merkmale werden von der-Klasse `Tr`bestimmt.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream-Programmierung](../standard-library/iostream-programming.md)\
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)

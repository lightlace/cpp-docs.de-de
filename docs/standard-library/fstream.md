---
title: '&lt;fstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <fstream>
helpviewer_keywords:
- fstream header
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
ms.openlocfilehash: 1f85367b9ae527c9387d085acc1496bfbbf7cc9e
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688041"
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
|[filebuf](../standard-library/fstream-typedefs.md#filebuf)|Ein Typ `basic_filebuf` spezialisiert auf **char** -Vorlagen Parameter.|
|[fstream](../standard-library/fstream-typedefs.md#fstream)|Ein Typ `basic_fstream` spezialisiert auf **char** -Vorlagen Parameter.|
|[ifstream](../standard-library/fstream-typedefs.md#ifstream)|Ein Typ `basic_ifstream` spezialisiert auf **char** -Vorlagen Parameter.|
|[ofstream](../standard-library/fstream-typedefs.md#ofstream)|Ein Typ `basic_ofstream` spezialisiert auf **char** -Vorlagen Parameter.|
|[wfstream](../standard-library/fstream-typedefs.md#wfstream)|Ein Typ `basic_fstream` spezialisiert auf **wchar_t** -Vorlagen Parameter.|
|[wifstream](../standard-library/fstream-typedefs.md#wifstream)|Ein Typ `basic_ifstream` spezialisiert auf **wchar_t** -Vorlagen Parameter.|
|[wofstream](../standard-library/fstream-typedefs.md#wofstream)|Ein Typ `basic_ofstream` spezialisiert auf **wchar_t** -Vorlagen Parameter.|
|[wfilebuf](../standard-library/fstream-typedefs.md#wfilebuf)|Ein Typ `basic_filebuf` spezialisiert auf **wchar_t** -Vorlagen Parameter.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[basic_filebuf](../standard-library/basic-filebuf-class.md)|Die Klassen Vorlage beschreibt einen Streampuffer, der die Übertragung von Elementen des Typs `Elem` steuert, dessen Zeichen Merkmale durch die Klasse `Tr` bestimmt werden, in eine und aus einer Sequenz von Elementen, die in einer externen Datei gespeichert sind.|
|[basic_fstream](../standard-library/basic-fstream-class.md)|Die Klassen Vorlage beschreibt ein Objekt, das das Einfügen und Extrahieren von Elementen und codierten Objekten mit einem Streampuffer der Klasse [Basic_filebuf](../standard-library/basic-filebuf-class.md) \<**Elem**, **TR**> mit Elementen des Typs `Elem` steuert, dessen Zeichen Merkmale werden durch die `Tr` der-Klasse bestimmt.|
|[basic_ifstream](../standard-library/basic-ifstream-class.md)|Die Klassen Vorlage beschreibt ein Objekt, das das Extrahieren von Elementen und codierten Objekten aus einem Streampuffer der Klasse [Basic_filebuf](../standard-library/basic-filebuf-class.md) \<**Elem**, **TR**> mit Elementen des Typs `Elem` steuert, dessen Zeichen Merkmale bestimmt durch die-Klasse `Tr`.|
|[basic_ofstream](../standard-library/basic-ofstream-class.md)|Die Klassen Vorlage beschreibt ein Objekt, das das Einfügen von Elementen und codierten Objekten in einen Streampuffer der Klasse [Basic_filebuf](../standard-library/basic-filebuf-class.md) \<**Elem**, **TR**> mit Elementen des Typs `Elem` steuert, dessen Zeichen Merkmale bestimmt werden. durch die-Klasse `Tr`.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream-Programmierung](../standard-library/iostream-programming.md)\
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)

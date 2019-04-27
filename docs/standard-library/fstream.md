---
title: '&lt;fstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <fstream>
helpviewer_keywords:
- fstream header
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
ms.openlocfilehash: 20efdc755b7f706fc6ee962daa32bd352df39d45
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159768"
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
|[filebuf](../standard-library/fstream-typedefs.md#filebuf)|Ein Typ `basic_filebuf` auf **Char** Vorlagenparameter.|
|[fstream](../standard-library/fstream-typedefs.md#fstream)|Ein Typ `basic_fstream` auf **Char** Vorlagenparameter.|
|[ifstream](../standard-library/fstream-typedefs.md#ifstream)|Ein Typ `basic_ifstream` auf **Char** Vorlagenparameter.|
|[ofstream](../standard-library/fstream-typedefs.md#ofstream)|Ein Typ `basic_ofstream` auf **Char** Vorlagenparameter.|
|[wfstream](../standard-library/fstream-typedefs.md#wfstream)|Ein Typ `basic_fstream` auf **"wchar_t"** Vorlagenparameter.|
|[wifstream](../standard-library/fstream-typedefs.md#wifstream)|Ein Typ `basic_ifstream` auf **"wchar_t"** Vorlagenparameter.|
|[wofstream](../standard-library/fstream-typedefs.md#wofstream)|Ein Typ `basic_ofstream` auf **"wchar_t"** Vorlagenparameter.|
|[wfilebuf](../standard-library/fstream-typedefs.md#wfilebuf)|Ein Typ `basic_filebuf` auf **"wchar_t"** Vorlagenparameter.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[basic_filebuf](../standard-library/basic-filebuf-class.md)|Die Vorlagenklasse beschreibt einen die Übertragung zu und aus einer Sequenz von in einer externen Datei gespeicherten Elementen von Elementen des Typs `Elem` steuernden Streampuffer, dessen Zeichenmerkmale durch die Klasse `Tr` ermittelt werden.|
|[basic_fstream](../standard-library/basic-fstream-class.md)|Die Vorlagenklasse beschreibt ein Objekt, das steuert, Einfügung und Extraktion von Elementen und codierten Objekten mit einem Streampuffer der Klasse [Basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**,  **TR**>, mit Elementen des Typs `Elem`, dessen Zeichenmerkmale von der Klasse ermittelt werden `Tr`.|
|[basic_ifstream](../standard-library/basic-ifstream-class.md)|Die Vorlagenklasse beschreibt ein Objekt, das steuert, Extrahieren von Elementen und codierten Objekten aus einem Streampuffer der Klasse [Basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**>, mit Elementen des Typs `Elem`, dessen Zeichenmerkmale von der Klasse ermittelt werden `Tr`.|
|[basic_ofstream](../standard-library/basic-ofstream-class.md)|Die Vorlagenklasse beschreibt ein Objekt, das steuert, Einfügen von Elementen und codierten Objekten in einen Streampuffer der Klasse [Basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**>, mit Elementen des Typs `Elem`, dessen Zeichenmerkmale von der Klasse ermittelt werden `Tr`.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream-Programmierung](../standard-library/iostream-programming.md)<br/>
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)<br/>

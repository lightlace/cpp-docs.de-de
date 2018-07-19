---
title: '&lt;fstream&gt; | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <fstream>
dev_langs:
- C++
helpviewer_keywords:
- fstream header
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6b716248c6fe9d0734cd580800c9254cf01f2a17
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962873"
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

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
ms.openlocfilehash: 3d2fa3ef6113add6bcf72f85f74b8722033cb8d5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
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
|[filebuf](../standard-library/fstream-typedefs.md#filebuf)|Ein `basic_filebuf`-Typ, der auf `char`-Vorlagenparameter spezialisiert ist.|
|[fstream](../standard-library/fstream-typedefs.md#fstream)|Ein `basic_fstream`-Typ, der auf `char`-Vorlagenparameter spezialisiert ist.|
|[ifstream](../standard-library/fstream-typedefs.md#ifstream)|Ein `basic_ifstream`-Typ, der auf `char`-Vorlagenparameter spezialisiert ist.|
|[ofstream](../standard-library/fstream-typedefs.md#ofstream)|Ein `basic_ofstream`-Typ, der auf `char`-Vorlagenparameter spezialisiert ist.|
|[wfstream](../standard-library/fstream-typedefs.md#wfstream)|Ein `basic_fstream`-Typ, der auf `wchar_t`-Vorlagenparameter spezialisiert ist.|
|[wifstream](../standard-library/fstream-typedefs.md#wifstream)|Ein `basic_ifstream`-Typ, der auf `wchar_t`-Vorlagenparameter spezialisiert ist.|
|[wofstream](../standard-library/fstream-typedefs.md#wofstream)|Ein `basic_ofstream`-Typ, der auf `wchar_t`-Vorlagenparameter spezialisiert ist.|
|[wfilebuf](../standard-library/fstream-typedefs.md#wfilebuf)|Ein `basic_filebuf`-Typ, der auf `wchar_t`-Vorlagenparameter spezialisiert ist.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[basic_filebuf](../standard-library/basic-filebuf-class.md)|Die Vorlagenklasse beschreibt einen Streampuffer, der steuert, wie Elemente des Typs **Elem**, dessen Zeichenmerkmale durch die Klasse **Tr** bestimmt sind, in eine oder aus einer Sequenz von Elementen übertragen werden, die in einer externen Datei gespeichert sind.|
|[basic_fstream](../standard-library/basic-fstream-class.md)|Die Vorlagenklasse beschreibt ein Objekt, das das Einfügen und Extrahieren von Elementen und codierten Objekten mit einem Streampuffer der Klasse [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**> mit Elementen des Typs **Elem** steuert, dessen Zeichenmerkmale durch die Klasse **Tr** bestimmt sind.|
|[basic_ifstream](../standard-library/basic-ifstream-class.md)|Die Vorlagenklasse beschreibt ein Objekt, das das Extrahieren von Elementen und codierten Objekten aus einem Streampuffer der Klasse [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**> mit Elementen des Typs **Elem** steuert, dessen Zeichenmerkmale durch die Klasse **Tr** bestimmt sind.|
|[basic_ofstream](../standard-library/basic-ofstream-class.md)|Die Vorlagenklasse beschreibt ein Objekt, das das Extrahieren von Elementen und codierten Objekten aus einem Streampuffer der Klasse [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**> mit Elementen des Typs **Elem** steuert, dessen Zeichenmerkmale durch die Klasse **Tr** bestimmt sind.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream-Programmierung](../standard-library/iostream-programming.md)<br/>
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)<br/>

---
title: '&lt;streambuf&gt;'
ms.date: 11/04/2016
f1_keywords:
- <streambuf>
helpviewer_keywords:
- streambuf header
ms.assetid: 4365b25c-5831-488b-b9c2-867bfe961b89
ms.openlocfilehash: ca5f53d67bb32e59c20d1d440879144f0a617c66
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72686021"
---
# <a name="ltstreambufgt"></a>&lt;streambuf&gt;

Fügen Sie den Iostreams-Standard Header \<streambuf > ein, um die Klassen Vorlage [basic_streambuf](../standard-library/basic-streambuf-class.md)zu definieren, die für den Betrieb der iostreams-Klassen einfach ist. Dieser Header wird in der Regel von einem der anderen iostreams-Header für Sie eingefügt. Sie müssen ihn nur selten direkt einfügen.

## <a name="syntax"></a>Syntax

```cpp
#include <streambuf>
```

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[streambuf](../standard-library/streambuf-typedefs.md#streambuf)|Eine Spezialisierung von `basic_streambuf`, die **char** als Vorlagen Parameter verwendet.|
|[wstreambuf](../standard-library/streambuf-typedefs.md#wstreambuf)|Eine Spezialisierung von `basic_streambuf`, die **wchar_t** als Vorlagen Parameter verwendet.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[basic_streambuf-Klasse](basic-streambuf-class.md)|Die Klassen Vorlage beschreibt eine abstrakte Basisklasse für die Ableitung eines Streampuffers, der die Übertragung von Elementen in eine und aus einer bestimmten Darstellung eines Streams steuert.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream-Programmierung](../standard-library/iostream-programming.md)\
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)

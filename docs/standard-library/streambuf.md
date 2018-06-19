---
title: '&lt;streambuf&gt; | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <streambuf>
dev_langs:
- C++
helpviewer_keywords:
- streambuf header
ms.assetid: 4365b25c-5831-488b-b9c2-867bfe961b89
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f4f2b455b362bcb170a09c89a0bfef8013286971
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33855265"
---
# <a name="ltstreambufgt"></a>&lt;streambuf&gt;

Fügen Sie den iostreams-Standardheader \<streambuf> ein, um die Vorlagenklasse [basic_streambuf](../standard-library/basic-streambuf-class.md) zu definieren, die die Basis für die Verwendung der iostreams-Klassen ist. Dieser Header wird in der Regel von einem der anderen iostreams-Header für Sie eingefügt. Sie müssen ihn nur selten direkt einfügen.

## <a name="syntax"></a>Syntax

```cpp
#include <streambuf>

```

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[streambuf](../standard-library/streambuf-typedefs.md#streambuf)|Eine Spezialisierung von `basic_streambuf`, die `char` als Vorlagenparameter verwendet.|
|[wstreambuf](../standard-library/streambuf-typedefs.md#wstreambuf)|Eine Spezialisierung von `basic_streambuf`, die `wchar_t` als Vorlagenparameter verwendet.|

### <a name="classes"></a>Klassen

|Klasse|Beschreibung|
|-|-|
|[basic_streambuf-Klasse](http://msdn.microsoft.com/en-us/d9c706ba-ce01-43e0-b0b2-a558fc53ea8d)|Die Vorlagenklasse beschreibt eine abstrakte Basisklasse für die Ableitung eines Streampuffers, der die Übertragung von Elementen in eine und aus einer bestimmten Darstellung eines Streams steuert.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream-Programmierung](../standard-library/iostream-programming.md)<br/>
[iostreams-Konventionen](../standard-library/iostreams-conventions.md)<br/>

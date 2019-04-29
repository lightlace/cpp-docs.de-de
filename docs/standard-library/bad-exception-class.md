---
title: bad_exception-Klasse
ms.date: 11/04/2016
f1_keywords:
- exception/std::bad_exception
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: 94d1104b66fc6bd84e209caa23ce309cffd9fa85
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62377817"
---
# <a name="badexception-class"></a>bad_exception-Klasse

Die Klasse beschreibt eine Ausnahme, die von einem unexpected-Handler ausgelöst werden kann.

## <a name="syntax"></a>Syntax

```cpp
class bad_exception    : public exception {};
```

## <a name="remarks"></a>Hinweise

[unexpected](../standard-library/exception-functions.md#unexpected) löst `bad_exception` aus, anstatt zu terminieren oder eine andere mit [set_unexpected](../standard-library/exception-functions.md#set_unexpected) angegebene Funktion aufzurufen, wenn `bad_exception` in der Auslöseliste einer Funktion enthalten ist.

Der Rückgabewert von `what` ist eine implementierungsdefinierte C-Zeichenfolge. Keine der Memberfunktionen löst irgendeine Ausnahme aus.

Sie finden eine Liste der Member, die von der `bad_exception`-Klasse geerbt werden, unter [exception-Klasse](../standard-library/exception-class.md).

## <a name="example"></a>Beispiel

Ein Beispiel zur Verwendung von [unexpected](../standard-library/exception-functions.md#unexpected), das `bad_exception` auslöst, finden Sie unter [set_unexpected](../standard-library/exception-functions.md#set_unexpected).

## <a name="requirements"></a>Anforderungen

**Header:** \<exception>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[exception-Klasse](../standard-library/exception-class.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>

---
title: bad_exception-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- exception/std::bad_exception
dev_langs:
- C++
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41b30763f1382b7a12f68cd6a45b87960f623649
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="badexception-class"></a>bad_exception-Klasse

Die Klasse beschreibt eine Ausnahme, die von einem unexpected-Handler ausgelöst werden kann.

## <a name="syntax"></a>Syntax

```cpp
class bad_exception    : public exception {};
```

## <a name="remarks"></a>Hinweise

[unexpected](../standard-library/exception-functions.md#unexpected) löst `bad_exception` aus, anstatt zu terminieren oder eine andere mit [set_unexpected](../standard-library/exception-functions.md#set_unexpected) angegebene Funktion aufzurufen, wenn `bad_exception` in der Auslöseliste einer Funktion enthalten ist.

Der von **what** zurückgegebene Wert ist eine durch die Implementierung definierte C-Zeichenfolge. Keine der Memberfunktionen löst irgendeine Ausnahme aus.

Sie finden eine Liste der Member, die von der `bad_exception`-Klasse geerbt werden, unter [exception-Klasse](../standard-library/exception-class.md).

## <a name="example"></a>Beispiel

Ein Beispiel zur Verwendung von [unexpected](../standard-library/exception-functions.md#unexpected), das `bad_exception` auslöst, finden Sie unter [set_unexpected](../standard-library/exception-functions.md#set_unexpected).

## <a name="requirements"></a>Anforderungen

**Header:** \<exception>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[exception-Klasse](../standard-library/exception-class.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>

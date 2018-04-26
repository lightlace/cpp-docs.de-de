---
title: bad_exception-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- exception/std::bad_exception
dev_langs:
- C++
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3b1b332b4f76f24f873fd8a57d302fc2643a71f1
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
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

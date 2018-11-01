---
title: bad_alloc-Klasse
ms.date: 11/04/2016
f1_keywords:
- new/std::bad_alloc
helpviewer_keywords:
- bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
ms.openlocfilehash: 1ebb427277c985fdab711d5bd84dcea54898a83b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515608"
---
# <a name="badalloc-class"></a>bad_alloc-Klasse

Die Klasse beschreibt eine Ausnahme, die ausgelöst wurde, um anzugeben, dass eine Belegungsanforderung nicht erfolgreich war.

## <a name="syntax"></a>Syntax

```cpp
class bad_alloc : public exception {
    bad_alloc();
virtual ~bad_alloc();

};
```

## <a name="remarks"></a>Hinweise

Der Rückgabewert von `what` ist eine implementierungsdefinierte C-Zeichenfolge. Keine der Memberfunktionen löst irgendeine Ausnahme aus.

## <a name="requirements"></a>Anforderungen

**Header:** \<new>

**Namespace:** std

## <a name="example"></a>Beispiel

```cpp
// bad_alloc.cpp
// compile with: /EHsc
#include<new>
#include<iostream>
using namespace std;

int main() {
   char* ptr;
   try {
      ptr = new char[(~unsigned int((int)0)/2) - 1];
      delete[] ptr;
   }
   catch( bad_alloc &ba) {
      cout << ba.what( ) << endl;
   }
}
```

## <a name="sample-output"></a>Beispielausgabe

```Output
bad allocation
```

## <a name="requirements"></a>Anforderungen

**Header:** \<new>

## <a name="see-also"></a>Siehe auch

[exception-Klasse](../standard-library/exception-class.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)

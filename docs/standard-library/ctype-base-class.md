---
title: ctype_base-Klasse
ms.date: 11/04/2016
f1_keywords:
- locale/std::ctype_base
helpviewer_keywords:
- ctype_base class
ms.assetid: ccffe891-d7ab-4d22-baf8-8eb6d438a96d
ms.openlocfilehash: 83ef35f9fac438cfa217decf222abd365ff84269
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394181"
---
# <a name="ctypebase-class"></a>ctype_base-Klasse

Die Klasse dient als Basisklasse für Facets der Vorlagenklasse [ctype](../standard-library/ctype-class.md). Eine Basisklasse für die ctype-Klasse, die verwendet wird, um die Enumerationstypen zu definieren, mit denen Zeichen entweder einzeln oder innerhalb eines gesamten Bereichs klassifiziert oder getestet werden.

## <a name="syntax"></a>Syntax

```cpp
struct ctype_base : public locale::facet
{
    enum
    {
        alnum,
        alpha,
        cntrl,
        digit,
        graph,
        lower,
        print,
        punct,
        space,
        upper,
        xdigit
    };
    typedef short mask;

    ctype_base( size_t _Refs = 0 );
    ~ctype_base();
};
```

## <a name="remarks"></a>Hinweise

Definiert eine Enumerationsmaske. Jede Enumerationskonstante kennzeichnet eine andere Möglichkeit zum Klassifizieren von Zeichen, wie durch die im Header \<ctype.h> deklarierten Funktionen mit ähnlichen Namen definiert. Folgende Konstanten können verwendet werden:

- **space** ([isspace](../standard-library/locale-functions.md#isspace)-Funktion)

- **print** ([isprint](../standard-library/locale-functions.md#isprint)-Funktion)

- **cntrl** ([iscntrl](../standard-library/locale-functions.md#iscntrl)-Funktion)

- **upper** ([isupper](../standard-library/locale-functions.md#isupper)-Funktion)

- **lower** ([islower](../standard-library/locale-functions.md#islower)-Funktion)

- **digit** ([isdigit](../standard-library/locale-functions.md#isdigit)-Funktion)

- **punct** ([ispunct](../standard-library/locale-functions.md#ispunct)-Funktion)

- **xdigit** ([isxdigit](../standard-library/locale-functions.md#isxdigit)-Funktion)

- **alpha** ([isalpha](../standard-library/locale-functions.md#isalpha)-Funktion)

- **alnum** ([isalnum](../standard-library/locale-functions.md#isalnum)-Funktion)

- **graph** ([isgraph](../standard-library/locale-functions.md#isgraph)-Funktion)

Eine Kombination von Klassifikationen kann durch Verknüpfen dieser Konstanten mit OR beschrieben werden. Es ist immer, die "true" **Alnum** == ( **Alpha** &#124; **Ziffer** \) und **Graph** \= \= \( **Alnum** &#124; **Punct**).

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>

---
title: messages_base-Klasse
ms.date: 11/04/2016
f1_keywords:
- xlocmes/std::messages_base
helpviewer_keywords:
- messages_base class
ms.assetid: 9aad38c6-4c13-445d-b096-364bd0836efb
ms.openlocfilehash: 79b6cb5f0b0c219e959f53fdc667f4c8af273cef
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451852"
---
# <a name="messagesbase-class"></a>messages_base-Klasse

Die Basisklasse beschreibt einen **int** -Typ für den Katalog von Meldungen.

## <a name="syntax"></a>Syntax

```cpp
struct messages_base : locale::facet {
    typedef int catalog;
    explicit messages_base(size_t _Refs = 0)
};
```

## <a name="remarks"></a>Hinweise

Der typkatalog ist ein Synonym für den Typ " **int** ", der die möglichen Rückgabewerte von "Messages:: [Do_open](../standard-library/messages-class.md#do_open)" beschreibt.

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)

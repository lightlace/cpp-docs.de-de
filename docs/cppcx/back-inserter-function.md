---
title: back_inserter-Funktion
ms.date: 12/30/2016
f1_keywords:
- collection/Windows::Foundation::Collections::back_inserter
helpviewer_keywords:
- back_inserter Function
ms.assetid: 91476338-5548-44b7-bc7e-2150f4fbe31a
ms.openlocfilehash: 82df6b06389fa9f1c3ab83fa7b1da3bab092c68d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209441"
---
# <a name="backinserter-function"></a>back_inserter-Funktion

Gibt einen Iterator zurück, der dazu verwendet wird, Elemente am Ende der angegebenen Auflistung einzufügen.

## <a name="syntax"></a>Syntax

```

template <typename T>
Platform::BackInsertIterator<T>
    back_inserter(IVector<T>^ v);

template<typename T>
Platform::BackInsertIterator<T>
   back_inserter(IObservableVector<T>^ v);
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Ein Vorlagentyp-Parameter.

*v*<br/>
Ein Schnittstellenzeiger, der Zugriff auf die zugrunde liegende Auflistung bietet.

### <a name="return-value"></a>Rückgabewert

Ein Iterator.

### <a name="requirements"></a>Anforderungen

**Header:** collection.h

**Namespace:** Windows::Foundation::Collections

## <a name="see-also"></a>Siehe auch

[Windows::Foundation::Collections-Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)

---
title: Back_inserter-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
f1_keywords:
- collection/Windows::Foundation::Collections::back_inserter
dev_langs:
- C++
helpviewer_keywords:
- back_inserter Function
ms.assetid: 91476338-5548-44b7-bc7e-2150f4fbe31a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c013c769e4fc25ed1c8770bf5727a26da590680
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106424"
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

[Collections-Namespace](../cppcx/windows-foundation-collections-namespace-c-cx.md)
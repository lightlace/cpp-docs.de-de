---
title: AsWeak-Funktion
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::AsWeak
helpviewer_keywords:
- AsWeak function
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
ms.openlocfilehash: 1332aa140a8298590ad83158e0ec1b75035c4e92
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54337373"
---
# <a name="asweak-function"></a>AsWeak-Funktion

Ruft einen schwachen Verweis zur angegebenen Instanz ab.

## <a name="syntax"></a>Syntax

```cpp
template<typename T>
HRESULT AsWeak(
   _In_ T* p,
   _Out_ WeakRef* pWeak
);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Ein Zeiger auf den Typ des Parameters *p*.

*p*<br/>
Eine Instanz eines Typs.

*pWeak*<br/>
Wenn dieser Vorgang abgeschlossen ist, einen Zeiger auf einen schwachen Verweis auf Parameter *p*.

## <a name="return-value"></a>Rückgabewert

S_OK, wenn dieser Vorgang erfolgreich ist; andernfalls ein Fehler HRESULT, das die Ursache des Fehlers angibt.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](microsoft-wrl-namespace.md)
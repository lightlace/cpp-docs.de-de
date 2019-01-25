---
title: IID_PPV_ARGS_Helper-Funktion
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/IID_PPV_ARGS_Helper
helpviewer_keywords:
- IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
ms.openlocfilehash: 5ef4dd6c9db2d19e0c8a4143c5b4ed3f0ac75f6a
ms.sourcegitcommit: c85c8a1226d8fbbaa29f4691ed719f8e6cc6575c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2019
ms.locfileid: "54894119"
---
# <a name="iidppvargshelper-function"></a>IID_PPV_ARGS_Helper-Funktion

Stellt sicher, dass der Typ des angegebenen Arguments abgeleitet der `IUnknown` Schnittstelle.

> [!IMPORTANT]
> Diese Spezialisierung einer Klassenvorlage unterstützt die WRL-Infrastruktur und nicht direkt aus Ihrem Code verwendet werden soll. Verwendung [IID_PPV_ARGS](/windows/desktop/api/combaseapi/nf-combaseapi-iid_ppv_args) stattdessen.

## <a name="syntax"></a>Syntax

```cpp
template<typename T>
void** IID_PPV_ARGS_Helper(
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp
);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ des Arguments *pp*.

*pp*<br/>
Ein doppelt indirekter Zeiger.

## <a name="return-value"></a>Rückgabewert

Argument *pp* Umwandeln in einen Zeiger-auf-a-Zeiger auf **"void"**.

## <a name="remarks"></a>Hinweise

Es wird ein Fehler während der Kompilierung generiert, wenn der Vorlagenparameter *T* nicht abgeleitet `IUnknown`.

## <a name="requirements"></a>Anforderungen

**Header:** client.h


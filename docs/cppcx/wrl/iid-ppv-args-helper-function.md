---
title: IID_PPV_ARGS_Helper-Funktion
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/IID_PPV_ARGS_Helper
helpviewer_keywords:
- IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
ms.openlocfilehash: e7733ae6084b64c20dff5a2c35d7a31c614d6e44
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500507"
---
# <a name="iid_ppv_args_helper-function"></a>IID_PPV_ARGS_Helper-Funktion

Überprüft, ob der Typ des angegebenen Arguments von der `IUnknown` -Schnittstelle abgeleitet ist.

> [!IMPORTANT]
> Diese Vorlagen Spezialisierung unterstützt die WRL-Infrastruktur und ist nicht für die direkte Verwendung im Code vorgesehen. Verwenden Sie stattdessen [IID_PPV_ARGS](/windows/win32/api/combaseapi/nf-combaseapi-iid_ppv_args) .

## <a name="syntax"></a>Syntax

```cpp
template<typename T>
void** IID_PPV_ARGS_Helper(
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp
);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ des Arguments *PP*.

*pp*<br/>
Ein doppelt indirekter Zeiger.

## <a name="return-value"></a>Rückgabewert

Argument- *PP* -Umwandlung in einen Zeiger auf einen Zeiger auf " **void**".

## <a name="remarks"></a>Hinweise

Ein Kompilierzeitfehler wird generiert, wenn der Vorlagen Parameter *T* nicht von `IUnknown`abgeleitet ist.

## <a name="requirements"></a>Anforderungen

**Header:** client.h


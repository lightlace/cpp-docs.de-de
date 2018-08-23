---
title: IID_PPV_ARGS_Helper-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/IID_PPV_ARGS_Helper
dev_langs:
- C++
helpviewer_keywords:
- IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3d22d6a7fce670f7da7740b5f0678eafaa49f519
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42604022"
---
# <a name="iidppvargshelper-function"></a>IID_PPV_ARGS_Helper-Funktion

Stellt sicher, dass der Typ des angegebenen Arguments abgeleitet der `IUnknown` Schnittstelle.

> [!IMPORTANT]
> Diese Spezialisierung einer Klassenvorlage unterstützt die WRL-Infrastruktur und nicht direkt aus Ihrem Code verwendet werden soll. Verwendung [IID_PPV_ARGS](http://msdn.microsoft.com/library/windows/desktop/ee330727.aspx) stattdessen.

## <a name="syntax"></a>Syntax

```cpp
template<typename T>
void** IID_PPV_ARGS_Helper(
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp
);
```

### <a name="parameters"></a>Parameter

*T*  
Der Typ des Arguments *pp*.

*PP*  
Ein doppelt indirekter Zeiger.

## <a name="return-value"></a>Rückgabewert

Argument *pp* Umwandeln in einen Zeiger-auf-a-Zeiger auf **"void"**.

## <a name="remarks"></a>Hinweise

Es wird ein Fehler während der Kompilierung generiert, wenn der Vorlagenparameter *T* nicht abgeleitet `IUnknown`.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

## <a name="see-also"></a>Siehe auch

[Referenz (Windows-Runtime-Bibliothek)](http://msdn.microsoft.com/00000000-0000-0000-0000-000000000000)
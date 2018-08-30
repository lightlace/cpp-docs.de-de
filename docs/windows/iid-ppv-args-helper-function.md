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
ms.openlocfilehash: a6131cea7a7684036fd7183a79214c7c6936540b
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43218747"
---
# <a name="iidppvargshelper-function"></a>IID_PPV_ARGS_Helper-Funktion

Stellt sicher, dass der Typ des angegebenen Arguments abgeleitet der `IUnknown` Schnittstelle.

> [!IMPORTANT]
> Diese Spezialisierung einer Klassenvorlage unterstützt die WRL-Infrastruktur und nicht direkt aus Ihrem Code verwendet werden soll. Verwendung [IID_PPV_ARGS](https://msdn.microsoft.com/library/windows/desktop/ee330727.aspx) stattdessen.

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

[Referenz (Windows-Runtime-Bibliothek)](https://msdn.microsoft.com/00000000-0000-0000-0000-000000000000)
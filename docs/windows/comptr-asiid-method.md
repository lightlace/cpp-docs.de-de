---
title: 'Comptr:: Asiid-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 07/11/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::AsIID
dev_langs:
- C++
helpviewer_keywords:
- AsIID method
ms.assetid: d5a3cdb2-796d-4410-966a-847c0e8fb226
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d3dfa87d950a12f115fb157124765fa5fd06eced
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396104"
---
# <a name="comptrasiid-method"></a>ComPtr::AsIID-Methode

Gibt eine **ComPtr** Objekt, das die Schnittstelle, die die angegebene Schnittstellen-ID identifizierte darstellt.

## <a name="syntax"></a>Syntax

```cpp
WRL_NOTHROW HRESULT AsIID(
   REFIID riid,
   _Out_ ComPtr<IUnknown>* p
) const;
```

### <a name="parameters"></a>Parameter

*riid*<br/>
Eine Schnittstellen-ID.

*p*<br/>
Wenn das Objekt eine Schnittstelle verfügt, deren ID gleich *Riid*, ein doppelt indirekter Zeiger auf die angegebene Schnittstelle die *Riid* Parameter ist, andernfalls ein Zeiger auf `IUnknown`.

## <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[ComPtr-Klasse](../windows/comptr-class.md)
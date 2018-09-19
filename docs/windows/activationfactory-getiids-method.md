---
title: 'Activationfactory:: Getiids-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory::GetIids
dev_langs:
- C++
helpviewer_keywords:
- GetIids method
ms.assetid: 0983d709-d155-4d65-aae4-5b2c8bb0fede
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 49ef07365675ddb9cdedee1f6a2cdfb676188dc6
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42576708"
---
# <a name="activationfactorygetiids-method"></a>ActivationFactory::GetIids-Methode

Ruft ein Array von implementierten Schnittstellen-IDs ab.

## <a name="syntax"></a>Syntax

```cpp
STDMETHOD(
   GetIids
)(_Out_ ULONG *iidCount, _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);
```

### <a name="parameters"></a>Parameter

*iidCount*  
Wenn dieser Vorgang abgeschlossen ist, die Anzahl der interace-IDs in die *Iids* Array.

*IIDs*  
Wenn dieser Vorgang abgeschlossen ist, implementiert ein Array von Schnittstellen-IDs an.

## <a name="return-value"></a>Rückgabewert

„S_OK“ im Erfolgsfall, andernfalls ein HRESULT, das den Fehler beschreibt. E_OUTOFMEMORY ist möglicherweise ein Fehler HRESULT.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[ActivationFactory-Klasse](../windows/activationfactory-class.md)
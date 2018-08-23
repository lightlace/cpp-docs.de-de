---
title: 'Activationfactory:: QueryInterface-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory::QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- QueryInterface method
ms.assetid: 2a9b71aa-61c0-43f7-aa35-00f0ee0af031
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8783d30aa018e0b29705c4c6bdda3b9e2a47af4a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613231"
---
# <a name="activationfactoryqueryinterface-method"></a>ActivationFactory::QueryInterface-Methode

Ruft einen Zeiger auf die angegebene Schnittstelle ab.

## <a name="syntax"></a>Syntax

```cpp
STDMETHOD(
   QueryInterface
)(REFIID riid, _Deref_out_ void **ppvObject);
```

### <a name="parameters"></a>Parameter

*riid*  
Eine Schnittstellen-ID.

*ppvObject*  
Wenn dieser Vorgang abgeschlossen ist, ein Zeiger auf die Schnittstelle, die vom Parameter angegebene *Riid*.

## <a name="return-value"></a>Rückgabewert

„S_OK“ im Erfolgsfall, andernfalls ein HRESULT, das den Fehler beschreibt.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[ActivationFactory-Klasse](../windows/activationfactory-class.md)
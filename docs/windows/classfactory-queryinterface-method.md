---
title: 'ClassFactory:: QueryInterface-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory::QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- QueryInterface method
ms.assetid: 9593881f-4585-4d70-8ca6-b328918d4d6b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 80c369d5ccbcc9f83d0f3ff90769a3df5d7ec177
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603411"
---
# <a name="classfactoryqueryinterface-method"></a>ClassFactory::QueryInterface-Methode

Ruft einen Zeiger auf die Schnittstelle, die durch Parameter angegeben wird.

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
Wenn dieser Vorgang abgeschlossen ist, einen Zeiger auf die Schnittstelle, die vom Parameter angegebene *Riid*.

## <a name="return-value"></a>Rückgabewert

„S_OK“ im Erfolgsfall, andernfalls ein HRESULT, das den Fehler beschreibt.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[ClassFactory-Klasse](../windows/classfactory-class.md)
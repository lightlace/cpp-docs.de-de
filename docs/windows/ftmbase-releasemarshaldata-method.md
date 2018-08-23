---
title: 'Ftmbase:: ReleaseMarshalData-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::ReleaseMarshalData
dev_langs:
- C++
helpviewer_keywords:
- ReleaseMarshalData method
ms.assetid: a94f9940-183a-4fde-8504-d223f346a0a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c2d4bccbcd9f3c3b13fa8be0ccc7afa493751cd9
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593538"
---
# <a name="ftmbasereleasemarshaldata-method"></a>FtmBase::ReleaseMarshalData-Methode

Zerstört ein gemarshalltes Datenpaket.

## <a name="syntax"></a>Syntax

```cpp
STDMETHODIMP ReleaseMarshalData(
   __in IStream *pStm
) override;
```

### <a name="parameters"></a>Parameter

*pStm*  
Zeiger auf ein Stream, der enthält das Datenpaket zerstört werden soll.

## <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="requirements"></a>Anforderungen

**Header:** ftm.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[FtmBase-Klasse](../windows/ftmbase-class.md)
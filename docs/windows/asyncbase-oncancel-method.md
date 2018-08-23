---
title: 'Asyncbase:: OnCancel-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::OnCancel
dev_langs:
- C++
helpviewer_keywords:
- OnCancel method
ms.assetid: 4bd0b68e-a9df-4913-9f6c-e093ed55c3f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6297b2d9313a8bc2c7a4f90632affa054c49c662
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595266"
---
# <a name="asyncbaseoncancel-method"></a>AsyncBase::OnCancel-Methode

Ruft beim Überschreiben in einer abgeleiteten Klasse Bricht einen asynchronen Vorgang ab.

## <a name="syntax"></a>Syntax

```cpp
virtual void OnCancel(
   void
) = 0;
```

## <a name="requirements"></a>Anforderungen

**Header:** async.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[AsyncBase-Klasse](../windows/asyncbase-class.md)  
[AsyncBase::Cancel-Methode](../windows/asyncbase-cancel-method.md)
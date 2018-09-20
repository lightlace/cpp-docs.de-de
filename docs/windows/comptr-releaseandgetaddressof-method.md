---
title: 'Comptr:: Releaseandgetaddressof-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf
dev_langs:
- C++
helpviewer_keywords:
- ReleaseAndGetAddressOf method
ms.assetid: 3751dcb4-d50e-432c-89e4-e736be34d434
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7f4aee13808fd55c42319aab90c13af7922ed9d2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394834"
---
# <a name="comptrreleaseandgetaddressof-method"></a>ComPtr::ReleaseAndGetAddressOf-Methode

Gibt die Schnittstelle frei zugeordneten **comptr-Objekt** und ruft dann die Adresse der [Ptr_](../windows/comptr-ptr-data-member.md) Datenmember, der einen Zeiger auf die Schnittstelle enthält, die veröffentlicht wurde.

## <a name="syntax"></a>Syntax

```cpp
T** ReleaseAndGetAddressOf();
```

## <a name="return-value"></a>Rückgabewert

Die Adresse der [Ptr_](../windows/comptr-ptr-data-member.md) Datenmember dieses **ComPtr**.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[ComPtr-Klasse](../windows/comptr-class.md)<br/>
[ComPtr::ptr_-Datenmember](../windows/comptr-ptr-data-member.md)
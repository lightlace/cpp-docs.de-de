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
ms.openlocfilehash: e3efdce7cde39431a8d6f097aace2ed2f5a66b4d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42589946"
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

[ComPtr-Klasse](../windows/comptr-class.md)  
[ComPtr::ptr_-Datenmember](../windows/comptr-ptr-data-member.md)
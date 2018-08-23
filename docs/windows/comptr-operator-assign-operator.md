---
title: 'Comptr:: Operator = | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 1a0c2752-f7d8-4819-9443-07b88b69ef02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fb26a6d7449dae4abe28be5687cea7d84ece7b8d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42604842"
---
# <a name="comptroperator-operator"></a>ComPtr::operator=-Operator

Weist einen Wert mit dem aktuellen **ComPtr**.

## <a name="syntax"></a>Syntax

```cpp
WRL_NOTHROW ComPtr& operator=(
   decltype(__nullptr)  
);
WRL_NOTHROW ComPtr& operator=(
   _In_opt_ T *other
);
template <typename U>
WRL_NOTHROW ComPtr& operator=(
   _In_opt_ U *other
);
WRL_NOTHROW ComPtr& operator=(
   const ComPtr &other
);
template<class U>
WRL_NOTHROW ComPtr& operator=(
   const ComPtr<U>& other
);
WRL_NOTHROW ComPtr& operator=(
   _Inout_ ComPtr &&other
);
template<class U>
WRL_NOTHROW ComPtr& operator=(
   _Inout_ ComPtr<U>&& other
);
```

### <a name="parameters"></a>Parameter

*U*  
Eine Klasse.

*other*  
Ein Zeiger, Verweis oder Rvalue-Verweis auf einen Typ oder eine andere **ComPtr**.

## <a name="return-value"></a>Rückgabewert

Ein Verweis auf das aktuelle **ComPtr**.

## <a name="remarks"></a>Hinweise

Die erste Version dieses Operators weist einen leeren Wert der aktuellen **ComPtr**.

In der zweiten Version, ist der Zuweisen von Schnittstellenzeiger nicht identisch mit dem aktuellen **ComPtr** -Schnittstellenzeiger, der zweite Schnittstellenzeiger wird zugewiesen, mit dem aktuellen **ComPtr**.

In der dritten Version erhält der zuweisen Schnittstellenzeiger mit dem aktuellen **ComPtr**.

In der vierten Version ist der Schnittstellenzeiger des zuweisen Werts nicht identisch mit dem aktuellen **ComPtr** -Schnittstellenzeiger, der zweite Schnittstellenzeiger wird zugewiesen, mit dem aktuellen **ComPtr**.

Die fünfte Version ist ein Operator kopieren. Ein Verweis auf eine **ComPtr** zugewiesen ist, mit dem aktuellen **ComPtr**.

Die sechste Version ist ein Copy-Operator, der verwendet die move-Semantik; Ein Rvalue-Verweis auf eine **ComPtr** wenn keinerlei statisch ist, umgewandelt, und klicken Sie dann auf den aktuellen zugewiesen **ComPtr**.

Die siebte Version ist ein Copy-Operator, der verwendet die move-Semantik; Ein Rvalue-Verweis auf eine **ComPtr** vom Typ *U* ist statische dann umgewandelt und mit dem aktuellen zugewiesen **ComPtr**.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[ComPtr-Klasse](../windows/comptr-class.md)
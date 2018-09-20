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
ms.openlocfilehash: 177d6ebde6a4611e9a08dc3dade63bd6c3acc3fa
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401627"
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

*U*<br/>
Eine Klasse.

*other*<br/>
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
---
title: 'Comptrrefbase:: Operator IInspectable **-Operator | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**
dev_langs:
- C++
helpviewer_keywords:
- operator IInspectable** operator
ms.assetid: 06ac1051-606c-449b-a566-cac78ca53762
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d83580537a81b1c75f44e32e6aa43b2b014c8373
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="comptrrefbaseoperator-iinspectable-operator"></a>ComPtrRefBase::operator IInspectable**-Operator

Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
operator IInspectable**() const;
```

## <a name="remarks"></a>Hinweise

Wandelt das aktuelle [Ptr_](../windows/comptrrefbase-ptr-data-member.md) -Datenmember auf einen Zeiger-auf-a-Zeiger-to "iinspectable"-Schnittstelle.

Ein Fehler wird ausgegeben, wenn die aktuelle ComPtrRefBase von "iinspectable" abgeleitet werden, nicht.

Diese Umwandlung ist verfügbar nur, wenn **&#95; &#95; WRL_CLASSIC_COM &#95; &#95;**  definiert ist.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[ComPtrRefBase-Klasse](../windows/comptrrefbase-class.md)   
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)
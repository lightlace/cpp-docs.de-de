---
title: 'Dontusenewusemake:: Neuer Operator | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new
dev_langs:
- C++
helpviewer_keywords:
- operator new operator
ms.assetid: 6af07a0d-2271-430c-9d9b-5a4223fed049
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 59354062dded7792dca1cd84683bba64f6a64aa0
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39571424"
---
# <a name="dontusenewusemakeoperator-new-operator"></a>DontUseNewUseMake::operator new-Operator
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
void* operator new(  
   size_t,  
   _In_ void* placement  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *__unnamed0*  
 Einen unbenannten Parameter, der angibt, die Anzahl der Bytes an Arbeitsspeicher zugewiesen werden.  
  
 *Platzierung*  
 Der Typ, zugeordnet werden.  
  
## <a name="return-value"></a>Rückgabewert  
 Bietet eine Möglichkeit, zusätzliche Argumente zu übergeben, wenn Sie beim Überladen **neue**.  
  
## <a name="remarks"></a>Hinweise  
 Überlädt **neue** und verhindert, dass deren verwendeten `RuntimeClass`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [DontUseNewUseMake-Klasse](../windows/dontusenewusemake-class.md)   
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)
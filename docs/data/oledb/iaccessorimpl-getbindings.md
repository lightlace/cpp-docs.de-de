---
title: 'IAccessorImpl:: Getbindings | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IAccessorImpl.GetBindings
- ATL::IAccessorImpl::GetBindings
- IAccessorImpl::GetBindings
- GetBindings
- ATL.IAccessorImpl.GetBindings
dev_langs:
- C++
helpviewer_keywords:
- GetBindings method
ms.assetid: eb550077-77ef-450b-89f1-a2930cee6ab8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7e49d1b7b1ff313a1afc89dd39422d50a52342e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="iaccessorimplgetbindings"></a>IAccessorImpl::GetBindings
Gibt die grundlegende Spalten Bindungen aus der Consumer in einem Accessor zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(GetBindings)(HACCESSOR hAccessor,  
   DBACCESSORFLAGS* pdwAccessorFlags,  
   DBCOUNTITEM* pcBindings,  
   DBBINDING** prgBindings);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IAccessor::GetBindings](https://msdn.microsoft.com/en-us/library/ms721253.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IAccessorImpl-Klasse](../../data/oledb/iaccessorimpl-class.md)
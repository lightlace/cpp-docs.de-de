---
title: 'IRowsetUpdateImpl:: SetData | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- SetData
- IRowsetUpdateImpl::SetData
- IRowsetUpdateImpl.SetData
- ATL::IRowsetUpdateImpl::SetData
- ATL.IRowsetUpdateImpl.SetData
dev_langs:
- C++
helpviewer_keywords:
- SetData method
ms.assetid: 7288a8d1-a7cf-4957-b832-0f3b18fd0da4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: adb15394f4470e23c0ecec2e704829c973c7f3a9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetupdateimplsetdata"></a>IRowsetUpdateImpl::SetData
Legt Datenwerte in einer oder mehreren Spalten fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD (SetData )(HROW hRow,  
   HACCESSOR hAccessor,  
   void* pSrcData);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IRowsetChange:: SetData](https://msdn.microsoft.com/en-us/library/ms721232.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die [IRowsetChangeImpl:: SetData](../../data/oledb/irowsetchangeimpl-setdata.md) Methode jedoch enthält Zwischenspeichern der ursprünglichen Daten um entweder sofort oder verzögerte Verarbeitung des Vorgangs zu ermöglichen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetUpdateImpl-Klasse](../../data/oledb/irowsetupdateimpl-class.md)
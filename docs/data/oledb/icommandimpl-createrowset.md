---
title: 'ICommandImpl:: CreateRowset | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ICommandImpl::CreateRowset
- ICommandImpl.CreateRowset
- CreateRowset
dev_langs:
- C++
helpviewer_keywords:
- CreateRowset method
ms.assetid: a0890009-205e-4970-879f-01ed9d6a93f1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 45fcb53c6412f91c35ea26a5e7a732f5de2d3fcc
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="icommandimplcreaterowset"></a>ICommandImpl::CreateRowset
Wird aufgerufen, indem [Execute](../../data/oledb/icommandimpl-execute.md) um ein einzelnes Rowset zu erstellen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      template template <class RowsetClass  
      >  
HRESULT CreateRowset(IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset,  
   RowsetClass*& pRowsetObj);  
```  
  
#### <a name="parameters"></a>Parameter  
 `RowsetClass`  
 Ein Klassenmember für die Vorlage, des Benutzers Rowsetklasse darstellt. In der Regel vom Assistenten generiert.  
  
 `pUnkOuter`  
 [in] Ein Zeiger auf das Steuern der **IUnknown** Schnittstelle, wenn das Rowset als Teil eines Aggregats erstellt wird; andernfalls ist null.  
  
 `riid`  
 [in] Entspricht `riid` in `ICommand::Execute`.  
  
 `pParams`  
 [in/Out] Entspricht `pParams` in `ICommand::Execute`.  
  
 `pcRowsAffected`  
 Entspricht `pcRowsAffected` in `ICommand::Execute`.  
  
 `ppRowset`  
 [in/Out] Entspricht `ppRowset` in `ICommand::Execute`.  
  
 `pRowsetObj`  
 [out] Ein Zeiger auf ein Rowsetobjekt. Dieser Parameter wird in der Regel nicht verwendet, jedoch kann verwendet werden, wenn Sie mehr Arbeit für das Rowset durchführen müssen, vor der Übergabe an ein COM-Objekt. Die Lebensdauer des `pRowsetObj` gebunden ist, indem Sie `ppRowset`.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert. Finden Sie unter `ICommand::Execute` eine Liste mit typischen Werten.  
  
## <a name="remarks"></a>Hinweise  
 Um mehr als ein Rowset zu erstellen oder eine eigene zum Erstellen von anderen Rowsets vorsehen, platzieren Sie unterschiedliche Aufrufe `CreateRowset` innerhalb **Execute**.  
  
 Finden Sie unter [ICommand:: Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) in die *OLE DB Programmer's Reference.*  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [ICommandImpl-Klasse](../../data/oledb/icommandimpl-class.md)
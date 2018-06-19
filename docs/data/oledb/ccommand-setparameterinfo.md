---
title: 'CCommand:: SetParameterInfo | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- SetParameterInfo
- CCommand.SetParameterInfo
- CCommand::SetParameterInfo
dev_langs:
- C++
helpviewer_keywords:
- SetParameterInfo method
ms.assetid: a70e92f4-1e73-41d7-a5b7-c6ebb45a6477
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a1bcbc30564b248991859ca2b1911e7b8a67dbe2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094526"
---
# <a name="ccommandsetparameterinfo"></a>CCommand::SetParameterInfo
Gibt den systemeigenen Typ eines jeden Befehlsparameter.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT CCommandBase::SetParameterInfo(DB_UPARAMS ulParams,  
   const DBORDINAL* pOrdinals,  
   const DBPARAMBINDINFO* pParamInfo) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [ICommandWithParameters:: SetParameterInfo](https://msdn.microsoft.com/en-us/library/ms725393.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CCommand-Klasse](../../data/oledb/ccommand-class.md)
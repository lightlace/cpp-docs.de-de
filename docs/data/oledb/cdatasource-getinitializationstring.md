---
title: 'CDataSource:: Getinitializationstring | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CDataSource::GetInitializationString
- CDataSource.GetInitializationString
- GetInitializationString
- CDataSource::GetInitializationString
- ATL.CDataSource.GetInitializationString
dev_langs:
- C++
helpviewer_keywords:
- GetInitializationString method
ms.assetid: 97134723-6e99-4004-a56d-ec57543dbf3b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f61bccdf583299f74d119da59447c3d4224a2b3b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="cdatasourcegetinitializationstring"></a>CDataSource::GetInitializationString
Ruft die Initialisierungszeichenfolge einer Datenquelle, die derzeit geöffnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetInitializationString(BSTR* pInitializationString,   
   bool bIncludePassword = false) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 *pInitializationString*  
 [out] Ein Zeiger auf die Initialisierungszeichenfolge angibt.  
  
 *bIncludePassword*  
 [in] **"true"** Wenn Zeichenfolge ein Kennwort; enthält andernfalls **"false"**.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Die resultierende Initialisierungszeichenfolge kann verwendet werden, um diese datenquellenverbindung später erneut zu öffnen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDataSource-Klasse](../../data/oledb/cdatasource-class.md)
---
title: 'CEnumerator:: Find | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CEnumerator::Find
- ATL::CEnumerator::Find
- ATL.CEnumerator.Find
- CEnumerator.Find
dev_langs:
- C++
helpviewer_keywords:
- Find method
ms.assetid: 69a153af-d6c3-40fd-9018-27c7d2f344c6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 66298c4be2bb1e43aa37899fe652ccbf6694faae
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cenumeratorfind"></a>CEnumerator::Find
Sucht nach einem angegebenen Namen unter verfügbaren Anbietern.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      bool Find(TCHAR* szSearchName) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 *szSearchName*  
 [in] Der Name gesucht werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 **"true"** , wenn der Name gefunden wurde. andernfalls **"false"**.  
  
## <a name="remarks"></a>Hinweise  
 Dieser Name ordnet die **SOURCES_NAME** Mitglied der [ISourcesRowset](https://msdn.microsoft.com/en-us/library/ms715969.aspx) Schnittstelle.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CEnumerator-Klasse](../../data/oledb/cenumerator-class.md)
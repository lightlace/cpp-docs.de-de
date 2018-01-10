---
title: 'CEnumerator:: Find | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CEnumerator::Find
- ATL::CEnumerator::Find
- ATL.CEnumerator.Find
- CEnumerator.Find
dev_langs: C++
helpviewer_keywords: Find method
ms.assetid: 69a153af-d6c3-40fd-9018-27c7d2f344c6
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1d7c2deef184ef9e56dffcfba52ba2cbb2947519
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cenumeratorfind"></a>CEnumerator::Find
Sucht nach einem angegebenen Namen unter verfügbaren Anbietern.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      bool Find(   
   TCHAR* szSearchName    
) throw( );  
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
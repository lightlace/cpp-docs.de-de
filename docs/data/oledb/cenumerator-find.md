---
title: 'CEnumerator:: Find | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2466127dab53fa6646a4f149400e4318aed59970
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094481"
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
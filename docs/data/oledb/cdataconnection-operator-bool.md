---
title: 'CDataConnection:: Operator BOOL | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataConnection::operatorBOOL
- ATL::CDataConnection::operatorBOOL
- CDataConnection.operatorBOOL
- ATL.CDataConnection.operatorBOOL
dev_langs:
- C++
helpviewer_keywords:
- BOOL operator
- operator bool
ms.assetid: ad0bea7f-61ff-47f7-8127-32a31e3e9b9d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ae1aea9ed45a8ff9254952f0b820a66b792085c8
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="cdataconnectionoperator-bool"></a>CDataConnection::operator BOOL
Bestimmt, ob die aktuelle Sitzung geöffnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
operator BOOL() throw();  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Gibt **BOOL** (MFC-Typedef)-Wert. **"True"** bedeutet, dass die aktuelle Sitzung geöffnet ist **"False"** bedeutet, dass die aktuelle Sitzung geschlossen wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDataConnection-Klasse](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator bool](../../data/oledb/cdataconnection-operator-bool-ole-db.md)
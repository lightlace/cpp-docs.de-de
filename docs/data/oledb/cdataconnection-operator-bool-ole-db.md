---
title: 'CDataConnection:: Operator Bool (OLE DB) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
ms.assetid: e0791faf-2ed2-4dbb-9e68-3b9b5da2b7a7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 07302c63301a0dd57c68ce12062fb54973980099
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cdataconnectionoperator-bool-ole-db"></a>CDataConnection::operator bool (OLE DB)
Bestimmt, ob die aktuelle Sitzung geöffnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
operator bool() throw();  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Gibt eine `bool` (C++-Datentyp)-Wert. **"true"** bedeutet, dass die aktuelle Sitzung geöffnet ist **"false"** bedeutet, dass die aktuelle Sitzung geschlossen wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDataConnection-Klasse](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator bool](../../data/oledb/cdataconnection-operator-bool.md)
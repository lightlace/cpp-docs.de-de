---
title: 'CDataConnection:: Operator CSession&amp; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSession&
- CDataConnection::operatorCSession&
- CDataConnection.operatorCSession&
- operatorCSession&
dev_langs:
- C++
helpviewer_keywords:
- operator CSession&
- CSession& operator
ms.assetid: fba1e498-e482-4dda-8e0f-2542163bf627
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 53355a04217451594eb9ce22c4233d1c70333ea4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cdataconnectionoperator-csessionamp"></a>CDataConnection:: Operator CSession&amp;
Gibt einen Verweis auf die enthaltene `CSession` Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
operator const CSession&();  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Dieser Operator gibt einen Verweis auf die enthaltene `CSession` -Objekt, sodass Sie übergeben ein `CDataConnection` Objekt, in dem eine `CSession` Verweis wird erwartet.  
  
## <a name="example"></a>Beispiel  
 Haben eine Funktion (z. B. `func` unten), akzeptiert eine `CSession` Verweis können Sie **CSession &** übergeben eine `CDataConnection` stattdessen Objekt.  
  
 [!code-cpp[NVC_OLEDB_Consumer#5](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_1.cpp)]  
  
 [!code-cpp[NVC_OLEDB_Consumer#6](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_2.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDataConnection-Klasse](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CSession*](../../data/oledb/cdataconnection-operator-csession-star.md)
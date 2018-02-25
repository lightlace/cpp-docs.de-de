---
title: 'CDataConnection:: Operator CDataSource&amp; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDataSource&
- CDataConnection.operatorCDataSource&
- operatorCDataSource&
- CDataConnection::operatorCDataSource&
dev_langs:
- C++
helpviewer_keywords:
- CDataSource& operator
- operator & (CDataSource)
ms.assetid: 852faeee-f1b1-4465-9828-b261d1edf022
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 255d1fe1d6363277c300fee134c5c41473ee8c3b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cdataconnectionoperator-cdatasourceamp"></a>CDataConnection:: Operator CDataSource&amp;
Gibt einen Verweis auf die enthaltene `CDataSource` Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
operator const CDataSource&() throw();  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Dieser Operator gibt einen Verweis auf die enthaltene `CDataSource` -Objekt, sodass Sie übergeben ein `CDataConnection` Objekt, in dem eine `CDataSource` Verweis wird erwartet.  
  
## <a name="example"></a>Beispiel  
 Haben eine Funktion (z. B. `func` unten), akzeptiert eine `CDataSource` Verweis können Sie **CDataSource &** übergeben eine `CDataConnection` stattdessen Objekt.  
  
 [!code-cpp[NVC_OLEDB_Consumer#3](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_1.cpp)]  
  
 [!code-cpp[NVC_OLEDB_Consumer#4](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_2.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDataConnection-Klasse](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CDataSource*](../../data/oledb/cdataconnection-operator-cdatasource-star.md)
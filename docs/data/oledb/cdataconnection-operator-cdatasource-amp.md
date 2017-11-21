---
title: 'CDataConnection:: Operator CDataSource&amp; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataSource&
- CDataConnection.operatorCDataSource&
- operatorCDataSource&
- CDataConnection::operatorCDataSource&
dev_langs: C++
helpviewer_keywords:
- CDataSource& operator
- operator & (CDataSource)
ms.assetid: 852faeee-f1b1-4465-9828-b261d1edf022
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fc2309b7b97a97d19ff9a68895fef3ed3bda8b7c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cdataconnectionoperator-cdatasourceamp"></a>CDataConnection:: Operator CDataSource&amp;
Gibt einen Verweis auf die enthaltene `CDataSource` Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
operator const CDataSource&() throw( );  
  
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
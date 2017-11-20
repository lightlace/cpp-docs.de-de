---
title: 'CDataConnection:: Operator CDataSource * | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataSource*
- CDataConnection::operatorCDataSource*
- CDataConnection.operatorCDataSource*
- operatorCDataSource*
dev_langs: C++
helpviewer_keywords:
- CDataSource* operator
- operator * (CDataSource)
ms.assetid: 9118e324-e68d-45c5-a791-03f041d420ed
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3010f0774224cd02a35aeaa185bca32f370d5ba0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cdataconnectionoperator-cdatasource"></a>CDataConnection::operator CDataSource*
Gibt einen Zeiger auf die enthaltene `CDataSource` Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
operator const CDataSource*() throw( );  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Dieser Operator gibt einen Zeiger auf die enthaltene `CDataSource` -Objekt, sodass Sie übergeben ein `CDataConnection` Objekt, in dem eine `CDataSource` Zeiger erwartet wird.  
  
 Finden Sie unter [Operator CDataSource &](../../data/oledb/cdataconnection-operator-cdatasource-amp.md) ein Verwendungsbeispiel für.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDataConnection-Klasse](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CDataSource&](../../data/oledb/cdataconnection-operator-cdatasource-amp.md)
---
title: 'CDataConnection:: Operator CSession * | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataConnection.operatorCSession*
- CDataConnection::operatorCSession*
- operatorCSession*
- CSession*
dev_langs: C++
helpviewer_keywords:
- operator CSession*
- CSession* operator
ms.assetid: 0b0feede-5c3e-4835-be5b-03651597014d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8c4ad47ce5163291c45827d94c9e6f8d5904c847
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cdataconnectionoperator-csession"></a>CDataConnection::operator CSession*
Gibt einen Zeiger auf die enthaltene `CSession` Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
operator const CSession*() throw( );  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Dieser Operator gibt einen Zeiger auf die enthaltene `CSession` -Objekt, sodass Sie übergeben ein `CDataConnection` Objekt, in dem eine `CSession` Zeiger erwartet wird.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Operator-CSession &](../../data/oledb/cdataconnection-operator-csession-amp.md) ein Verwendungsbeispiel für.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDataConnection-Klasse](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CSession&](../../data/oledb/cdataconnection-operator-csession-amp.md)
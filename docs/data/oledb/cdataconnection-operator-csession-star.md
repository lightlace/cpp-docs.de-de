---
title: 'CDataConnection:: Operator CSession * | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataConnection.operatorCSession*
- CDataConnection::operatorCSession*
- operatorCSession*
- CSession*
dev_langs:
- C++
helpviewer_keywords:
- operator CSession*
- CSession* operator
ms.assetid: 0b0feede-5c3e-4835-be5b-03651597014d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 97219418f18220cde84c80cb9052f17552a3a45d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33094468"
---
# <a name="cdataconnectionoperator-csession"></a>CDataConnection::operator CSession*
Gibt einen Zeiger auf die enthaltene `CSession` Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
operator const CSession*() throw();  
  
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
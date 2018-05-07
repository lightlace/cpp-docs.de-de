---
title: 'CDataConnection:: Opennewsession | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataConnection.OpenNewSession
- ATL.CDataConnection.OpenNewSession
- ATL::CDataConnection::OpenNewSession
- OpenNewSession
- CDataConnection::OpenNewSession
dev_langs:
- C++
helpviewer_keywords:
- OpenNewSession method
ms.assetid: 0a70e573-9498-4ca7-b524-45666dc7b0a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f20f66ec6cc494c14e99c50de4824ba68d27264d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cdataconnectionopennewsession"></a>CDataConnection::OpenNewSession
Öffnet eine neue Sitzung mithilfe des aktuellen Verbindungsobjekts-Datenquelle.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT OpenNewSession(CSession & session) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `session`  
 [in/Out] Ein Verweis auf das Objekt für die neue Sitzung.  
  
 **Hinweise**  
 Die neue Sitzung verwendet das aktuelle Verbindungsobjekt enthaltenen Datenquellenobjekt wie das übergeordnete Objekt und kann auf alle die gleichen Informationen wie die Datenquelle zugreifen.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDataConnection-Klasse](../../data/oledb/cdataconnection-class.md)
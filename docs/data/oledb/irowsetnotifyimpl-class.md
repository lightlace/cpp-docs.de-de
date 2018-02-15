---
title: IRowsetNotifyImpl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetNotifyImpl
- ATL::IRowsetNotifyImpl
- IRowsetNotifyImpl
dev_langs:
- C++
helpviewer_keywords:
- IRowsetNotifyImpl class
ms.assetid: fbfd0cb2-38ff-4b42-899a-8de902f834b8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8e23103cf4505ffb2bc683c69d22628fa15b861d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="irowsetnotifyimpl-class"></a>IRowsetNotifyImpl-Klasse
Implementiert und registriert [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx) auf Consumer (auch bekannt als "Senke" genannt), damit es Benachrichtigungen behandeln kann.  
  
## <a name="syntax"></a>Syntax

```cpp
class ATL_NO_VTABLE IRowsetNotifyImpl : public IRowsetNotify  
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[OnFieldChange](../../data/oledb/irowsetnotifyimpl-onfieldchange.md)|Benachrichtigt den Consumer der Änderungen auf den Wert einer Spalte an.|  
|[OnRowChange](../../data/oledb/irowsetnotifyimpl-onrowchange.md)|Benachrichtigt den Consumer die erste Änderung an einer Zeile oder alle Änderungen, die die gesamte Zeile auswirkt.|  
|[OnRowsetChange](../../data/oledb/irowsetnotifyimpl-onrowsetchange.md)|Den Consumer alle Änderungen, die Auswirkungen auf das gesamte Rowset wird benachrichtigt.|  
  
## <a name="remarks"></a>Hinweise  
 Finden Sie unter [empfangen von Benachrichtigungen](../../data/oledb/receiving-notifications.md) zum Implementieren der Verbindungspunkt-Schnittstelle für den Consumer.  
  
 `IRowsetNotifyImpl` Stellt eine dummy-Implementierung für `IRowsetNotify`, mit leeren Funktionen für die `IRowsetNotify` Methoden [OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx), [OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx), und [OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx). Wenn Sie von dieser Klasse erben, wenn Sie implementieren eine `IRowsetNotify` -Schnittstelle, implementieren Sie nur die Methoden, die Sie benötigen. Sie müssen auch leere Implementierungen für die anderen Methoden selbst bereitstellen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx)   
 [IRowsetNotifyCP-Klasse](../../data/oledb/irowsetnotifycp-class.md)
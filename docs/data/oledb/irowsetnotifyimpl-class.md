---
title: IRowsetNotifyImpl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetNotifyImpl
- ATL::IRowsetNotifyImpl
- IRowsetNotifyImpl
dev_langs: C++
helpviewer_keywords: IRowsetNotifyImpl class
ms.assetid: fbfd0cb2-38ff-4b42-899a-8de902f834b8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7473e63c7ca67dff200d5cf96f1774ca9a2d6817
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetnotifyimpl-class"></a>IRowsetNotifyImpl-Klasse
Implementiert und registriert [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx) auf Consumer (auch bekannt als "Senke" genannt), damit es Benachrichtigungen behandeln kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
 `IRowsetNotifyImpl`Stellt eine dummy-Implementierung für `IRowsetNotify`, mit leeren Funktionen für die `IRowsetNotify` Methoden [OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx), [OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx), und [OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx). Wenn Sie von dieser Klasse erben, wenn Sie implementieren eine `IRowsetNotify` -Schnittstelle, implementieren Sie nur die Methoden, die Sie benötigen. Sie müssen auch leere Implementierungen für die anderen Methoden selbst bereitstellen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx)   
 [IRowsetNotifyCP-Klasse](../../data/oledb/irowsetnotifycp-class.md)
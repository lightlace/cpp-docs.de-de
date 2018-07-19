---
title: 'IRowsetNotifyCP:: Fire_onrowchange | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetNotifyCP.Fire_OnRowChange
- ATL.IRowsetNotifyCP.Fire_OnRowChange
- Fire_OnRowChange
- ATL::IRowsetNotifyCP::Fire_OnRowChange
- IRowsetNotifyCP::Fire_OnRowChange
dev_langs:
- C++
helpviewer_keywords:
- Fire_OnRowChange method
ms.assetid: 6f9beed6-7a69-4c92-936f-422e98f3de5c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 32c43a9cab81c117d63ec07bc4a352808eeffd8b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101847"
---
# <a name="irowsetnotifycpfireonrowchange"></a>IRowsetNotifyCP::Fire_OnRowChange
Überträgt ein [OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx) Ereignis an alle Listener auf dem Verbindungspunkt **IID_IRowsetNotify** eine Änderung der Auswirkungen auf die Zeilen Verbraucher darüber informieren.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT Fire_OnRowChange(IRowset* pRowset,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBREASON eReason,  
   DBEVENTPHASE ePhase,  
   BOOL fCantDeny);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IRowsetNotify::OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetNotifyCP-Klasse](../../data/oledb/irowsetnotifycp-class.md)
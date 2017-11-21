---
title: 'IRowsetNotifyImpl:: Onrowsetchange | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- OnRowsetChange
- IRowsetNotifyImpl::OnRowsetChange
- IRowsetNotifyImpl.OnRowsetChange
dev_langs: C++
helpviewer_keywords: OnRowsetChange method
ms.assetid: 5125b0c8-f175-4ee6-befa-8df2c904d5e0
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6073976867099ff683f1afdd3f4e593ffd5a8876
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetnotifyimplonrowsetchange"></a>IRowsetNotifyImpl::OnRowsetChange
Den Consumer alle Änderungen, die Auswirkungen auf das gesamte Rowset wird benachrichtigt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
   STDMETHOD(OnRowsetChange)(   
/* [in] */ IRowset* /* pRowset */,  
/* [in] */ DBREASON /* eReason */,  
/* [in] */ DBEVENTPHASE /* ePhase */,  
/* [in] */ BOOL /* fCantDeny */)  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IRowsetNotify::OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx) für parameterbeschreibungen.  
  
## <a name="return-value"></a>Rückgabewert  
 Finden Sie unter [IRowsetNotify::OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx) für zurückgeben Wert Beschreibungen.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode umschließt den [IRowsetNotify::OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx) Methode. Finden Sie in dieser Methode Beschreibung in der OLE DB Programmer's Reference Einzelheiten.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetNotifyImpl-Klasse](../../data/oledb/irowsetnotifyimpl-class.md)   
 [IRowsetNotify::OnRowsetChange](https://msdn.microsoft.com/en-us/library/ms722669.aspx)
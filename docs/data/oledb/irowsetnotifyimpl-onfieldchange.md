---
title: 'IRowsetNotifyImpl:: Onfieldchange | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetNotifyImpl.OnFieldChange
- IRowsetNotifyImpl::OnFieldChange
- OnFieldChange
dev_langs: C++
helpviewer_keywords: OnFieldChange method
ms.assetid: f26b492c-c86e-423b-9374-175e510a2860
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f6816ca96d3fe00e48d0fdca7b560eb628150d4d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetnotifyimplonfieldchange"></a>IRowsetNotifyImpl::OnFieldChange
Benachrichtigt den Consumer der Änderungen auf den Wert einer Spalte an.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
STDMETHOD(OnFieldChange)(   
/* [in] */ IRowset* /* pRowset */,  
/* [in] */ HROW /* hRow */,  
/* [in] */ DBORDINAL /* cColumns */,  
/* [size_is][in] */ DBORDINAL /* rgColumns */ [] ,  
/* [in] */ DBREASON /* eReason */,  
/* [in] */ DBEVENTPHASE /* ePhase */,  
/* [in] */ BOOL /* fCantDeny */)  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx) für parameterbeschreibungen.  
  
## <a name="return-value"></a>Rückgabewert  
 Finden Sie unter [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx) für zurückgeben Wert Beschreibungen.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode umschließt den [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx) Methode. Finden Sie in dieser Methode Beschreibung in der OLE DB Programmer's Reference Einzelheiten.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetNotifyImpl-Klasse](../../data/oledb/irowsetnotifyimpl-class.md)   
 [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx)
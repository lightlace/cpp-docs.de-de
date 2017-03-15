---
title: "IRowsetNotifyImpl::OnFieldChange | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetNotifyImpl.OnFieldChange"
  - "IRowsetNotifyImpl::OnFieldChange"
  - "OnFieldChange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnFieldChange-Methode"
ms.assetid: f26b492c-c86e-423b-9374-175e510a2860
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# IRowsetNotifyImpl::OnFieldChange
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Benachrichtigt den Consumer über alle Änderungen am Wert einer Spalte.  
  
## Syntax  
  
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
  
#### Parameter  
 Siehe [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx) für Parameterbeschreibungen.  
  
## Rückgabewert  
 Siehe [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx) für Rückgabewertbeschreibungen.  
  
## Hinweise  
 Diese Methode umschließt die Methode [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx) ein.  Siehe dazu die Beschreibung dieser Methode im OLE DB\-Programmierreferenz für Details.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [IRowsetNotifyImpl\-Klasse](../../data/oledb/irowsetnotifyimpl-class.md)   
 [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx)
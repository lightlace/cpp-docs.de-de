---
title: "IRowsetImpl::m_bReset"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "ATL.IRowsetImpl.m_bReset"
  - "IRowsetImpl.m_bReset"
  - "m_bReset"
  - "IRowsetImpl::m_bReset"
  - "ATL::IRowsetImpl::m_bReset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_bReset"
ms.assetid: d423f9f3-4d48-4d0c-b152-684c81a0b34e
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetImpl::m_bReset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Bitflag verwendet, um zu bestimmen, ob die Cursorposition im Rowset definiert wird.  
  
## Syntax  
  
```  
  
unsigned m_bReset:1;  
  
```  
  
## Hinweise  
 Wenn der Consumer [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) mit negativen `lOffset` aufruft, oder *Krähen* und `m_bReset` true ist, wird `GetNextRows` an das Ende des Rowsets.  Wenn `m_bReset` false ist, empfängt der Consumer einen Fehlercode, mit der OLE DB\-Spezifikation.  Das Flag `m_bReset` gelangt Satz an **true**, wenn das Rowset zuerst erstellt wird und wenn der Consumer [IRowsetImpl::RestartPosition](../../data/oledb/irowsetimpl-restartposition.md).  Es geht Satz an **false**, wenn Sie `GetNextRows` aufrufen.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [IRowsetImpl\-Klasse](../../data/oledb/irowsetimpl-class.md)
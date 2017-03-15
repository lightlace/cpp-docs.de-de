---
title: "CCommand::Unprepare | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Unprepare"
  - "CCommand.Unprepare"
  - "CCommand::Unprepare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unprepare-Methode"
ms.assetid: 4fe59988-fe51-4c7c-a156-72b68e3d642b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CCommand::Unprepare
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt den aktuellen Befehlsausführungsplan auf.  
  
## Syntax  
  
```  
  
HRESULT CCommandBase::Unprepare( ) throw( );  
  
```  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Diese Methode umschließt die OLE DB\-Methode [ICommandPrepare::Unprepare](https://msdn.microsoft.com/en-us/library/ms719635.aspx).  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CCommand\-Klasse](../../data/oledb/ccommand-class.md)
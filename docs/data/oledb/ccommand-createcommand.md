---
title: "CCommand::CreateCommand | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CCommand.CreateCommand"
  - "CreateCommand"
  - "CCommand::CreateCommand"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateCommand-Methode"
ms.assetid: 3652a313-07a1-40ec-82d6-fc7182f2a6f6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CCommand::CreateCommand
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt einen neuen Befehl.  
  
## Syntax  
  
```  
  
      HRESULT CCommandBase::CreateCommand(  
   const CSession& session   
) throw ( );  
```  
  
#### Parameter  
 `session`  
 \[in\] mit dem neuen Befehl zugeordnet Objekt A, `CSession`.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Diese Methode erstellt einen Befehl mithilfe des angegebenen Session\-Objekts.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CCommand\-Klasse](../../data/oledb/ccommand-class.md)
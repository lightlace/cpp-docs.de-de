---
title: "CCommand::ReleaseCommand | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CCommand.ReleaseCommand"
  - "ReleaseCommand"
  - "CCommand::ReleaseCommand"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseCommand-Methode"
ms.assetid: 3b58230c-13d5-45c5-b43e-bb013ecc3019
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CCommand::ReleaseCommand
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Befreit den Parameteraccessor, gibt dem Befehl selbst freigegeben.  
  
## Syntax  
  
```  
  
void CCommandBase::ReleaseCommand( ) throw( );  
  
```  
  
## Hinweise  
 `ReleaseCommand` wird in Verbindung mit **Schließen** verwendet.  Siehe [Schließen](../../data/oledb/ccommand-close.md) für Verwendungsdetails.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CCommand\-Klasse](../../data/oledb/ccommand-class.md)   
 [CCommand::Close](../../data/oledb/ccommand-close.md)
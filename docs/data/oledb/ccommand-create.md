---
title: "CCommand::Create | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CCommand.Create"
  - "CCommand::Create"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Create-Methode [C++]"
ms.assetid: e4bede7a-68bd-491a-97f4-89b03d45cd24
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CCommand::Create
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft [CCommand::CreateCommand](../../data/oledb/ccommand-createcommand.md) auf, um einen Befehl für die angegebene Sitzung zu erstellen, ruft [ICommandText::SetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) auf, um den Befehlstext anzugeben.  
  
## Syntax  
  
```  
  
      HRESULT CCommandBase::Create(  
   const CSession& session,   
   LPCWSTR wszCommand,   
   REFGUID guidCommand = DBGUID_DEFAULT  
) throw ( );  
HRESULT CCommandBase::Create(  
   const CSession& session,   
   LPCSTR szCommand,   
   REFGUID guidCommand = DBGUID_DEFAULT  
) throw ( );  
```  
  
#### Parameter  
 `session`  
 \[in\] auf der a\-Sitzung, um den Befehl zu erstellen.  
  
 `wszCommand`  
 \[in\] Ein Zeiger z Unicode\-Text der es sich standardmäßig um.  
  
 `szCommand`  
 \[in\] Ein Zeiger z ANSI\-Text der es sich standardmäßig um.  
  
 `guidCommand`  
 \[in\] Eine GUID, die der Syntax und die allgemeinen Regeln angibt, den der Anbieter verwendet, wenn es den Befehlstext analysiert.  Eine Beschreibung von Dialekten, finden Sie unter [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Das erste Format von **Erstellen** wird eine Unicode\-Befehlszeichenfolge.  Das zweite Format von **Erstellen** wird eine ANSI\-Befehlszeichenfolge \(bereitgestellt für Abwärtskompatibilität mit vorhandenen ANSI\-Anwendungen\).  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CCommand\-Klasse](../../data/oledb/ccommand-class.md)
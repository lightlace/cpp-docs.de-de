---
title: "ICommandImpl::GetDBSession | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ICommandImpl::GetDBSession"
  - "GetDBSession"
  - "ICommandImpl.GetDBSession"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetDBSession-Methode"
ms.assetid: e5b1cb13-453f-4698-90bf-f6bfe6814a54
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# ICommandImpl::GetDBSession
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt einen Schnittstellenzeiger auf die Sitzung zurückkehren, die den Befehl erstellt hat.  
  
## Syntax  
  
```  
  
      STDMETHOD (GetDBSession) (  
   REFIID riid,  
   IUnknown** ppSession   
);  
```  
  
#### Parameter  
 Siehe [ICommand::GetDBSession](https://msdn.microsoft.com/en-us/library/ms719622.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Hinweise  
 Wird für das Abrufen von Eigenschaften aus der Sitzung.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [ICommandImpl\-Klasse](../../data/oledb/icommandimpl-class.md)
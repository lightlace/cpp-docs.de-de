---
title: "ICommandImpl::Execute | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ICommandImpl::Execute"
  - "ICommandImpl.Execute"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Execute-Methode"
ms.assetid: 033e0d4e-256b-4eed-9215-70e0bebb768c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# ICommandImpl::Execute
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Führt den Befehl aus.  
  
## Syntax  
  
```  
  
      HRESULT Execute(  
   IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset   
);  
```  
  
#### Parameter  
 Siehe [ICommand::Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) in der *OLE* DB\-Programmierreferenz.  
  
## Hinweise  
 Die Ausgangsschnittstelle, die angefordert wird, ist eine Schnittstelle, die vom Rowsetobjekt abgerufen wird, die diese Funktion erstellt.  
  
 **Ausführen** Aufrufe [CreateRowset](../../data/oledb/icommandimpl-createrowset.md).  Überschreiben Sie die Standardimplementierung, um mehr als ein Rowset zu erstellen oder eigene Bedingungen zum Erstellen verschiedener Rowsets bereitzustellen.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [ICommandImpl\-Klasse](../../data/oledb/icommandimpl-class.md)   
 [ICommandImpl::CancelExecution](../../data/oledb/icommandimpl-cancelexecution.md)
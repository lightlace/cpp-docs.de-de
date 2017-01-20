---
title: "ICommandImpl-Klasse"
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
  - "ICommandImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICommandImpl-Klasse"
ms.assetid: ef285fef-0d66-45e6-a762-b03357098e3b
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# ICommandImpl-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt Implementierung für die [ICommand](https://msdn.microsoft.com/en-us/library/ms709737.aspx)\-Schnittstelle bereit.  
  
## Syntax  
  
```  
template <class T, class CommandBase = ICommand>   
class ATL_NO_VTABLE ICommandImpl : public CommandBase  
```  
  
#### Parameter  
 `T`  
 Die Klasse, von `ICommandImpl` abgeleitet.  
  
 `CommandBase`  
 Eine Befehlsschnittstelle.  Die Standardeinstellung ist `ICommand`.  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[CancelExecution](../../data/oledb/icommandimpl-cancelexecution.md)|Bricht die aktuelle Befehlsausführung ab.|  
|[Abbrechen](../../data/oledb/icommandimpl-cancel.md)|Bricht die aktuelle Befehlsausführung ab.|  
|[CreateRowset](../../data/oledb/icommandimpl-createrowset.md)|Erstellt ein Rowsetobjekt.|  
|[Ausführen](../../data/oledb/icommandimpl-execute.md)|Führt den Befehl aus.|  
|[GetDBSession](../../data/oledb/icommandimpl-getdbsession.md)|Gibt einen Schnittstellenzeiger auf die Sitzung zurückkehren, die den Befehl erstellt hat.|  
|[ICommandImpl](../../data/oledb/icommandimpl-icommandimpl.md)|Der \-Konstruktor.|  
  
### Datenmember  
  
|||  
|-|-|  
|[m\_bCancel](../../data/oledb/icommandimpl-m-bcancel.md)|Gibt an, ob der Befehl abgebrochen werden soll.|  
|[M\_bCancelWhenExecuting](../../data/oledb/icommandimpl-m-bcancelwhenexecuting.md)|Gibt an, ob der Befehl beim Ausführen abgebrochen werden soll.|  
|[M\_bIsExecuting](../../data/oledb/icommandimpl-m-bisexecuting.md)|Gibt an, ob der Befehl zur Zeit ausführt.|  
  
## Hinweise  
 Eine erforderliche Schnittstelle im Befehlsobjekt.  
  
## Anforderungen  
 **Header:**  atldb.h  
  
## Siehe auch  
 [OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)
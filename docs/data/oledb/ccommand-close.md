---
title: "CCommand::Close"
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
  - "CCommand.Close"
  - "CCommand::Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Close-Methode"
ms.assetid: 4da9c02c-7082-4e47-a0fa-78b546f0f7d2
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CCommand::Close
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt das Accessorrowset frei, das dem Befehl zugeordnet ist.  
  
## Syntax  
  
```  
void Close( );  
```  
  
## Hinweise  
 Ein Befehl verwendet ein Rowset, Resultsetaccessor und \(optional\) einen Parameteraccessor \(außer Tabellen, die keine Parameter unterstützen und keinen Parameteraccessor erfordern\).  
  
 Wenn Sie einen Befehl ausführen, müssen Sie `Close` und [ReleaseCommand](../../data/oledb/ccommand-releasecommand.md) nach dem Befehl aufrufen.  
  
 Wenn Sie den gleichen Befehl wiederholt ausführen möchten, sollten Sie jeden Resultsetaccessor freigeben, indem Sie `Close` aufrufen, bevor Sie `Execute` aufrufen.  Am Ende der Zeile, sollten Sie den Parameteraccessor schützen, indem Sie `ReleaseCommand` aufrufen.  Ein anderes allgemeines Szenario ruft eine gespeicherte Prozedur auf, die einzigen Ausgabeparameter.  Auf vielen Anbietern \(wie dem OLE DB\-Anbieter für SQL Server\) sind der Ausgabeparameterwerte nicht zugreifen, bis Sie den Resultsetaccessor schließen.  Rufen Sie `Close` auf, um den zurückgegebenen Rowset\- und Resultsetaccessor zu schließen, jedoch nicht den Parameteraccessor und Sie so können, um der Ausgabeparameterwerte.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie Sie `Close` und `ReleaseCommand` aufrufen können, wenn Sie den gleichen Befehl wiederholt ausführen.  
  
 [!CODE [NVC_OLEDB_Consumer#2](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#2)]  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CCommand\-Klasse](../../data/oledb/ccommand-class.md)   
 [CCommand::ReleaseCommand](../../data/oledb/ccommand-releasecommand.md)
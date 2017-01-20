---
title: "CCommand::GetNextResult"
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
  - "ATL::CCommand::GetNextResult"
  - "CCommand::GetNextResult"
  - "GetNextResult"
  - "CCommand.GetNextResult"
  - "ATL.CCommand.GetNextResult"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetNextResult-Methode"
ms.assetid: 63df9b55-9490-45c4-934a-879c5c2725d8
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CCommand::GetNextResult
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft Folgendes Resultset, wenn dieser verfügbar ist.  
  
## Syntax  
  
```  
  
      HRESULT GetNextResult(  
   DBROWCOUNT* pulRowsAffected,  
   bool bBind = true   
) throw( );  
```  
  
#### Parameter  
 *pulRowsAffected*  
 \[in\/out\] Ein Zeiger auf den Speicher, in dem die Anzahl von Zeilen, die über einen Befehl gelten, zurückgegeben wird.  
  
 `bBind`  
 \[in\] gibt an, ob der Befehl automatisch gebunden, nach ausgeführt werden.  Der Standardwert ist **true**, der den Befehl auslöst, automatisch gebunden werden.  Einstellung `bBind` von **false** verhindert die automatische Bindung des Befehls, damit Sie manuell binden können. \(Das manuelle Bindung ist von besonderem Interesse für OLAP\-Benutzern.\)  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Wenn ein Resultset zuvor abgerufen wurde, ungebunden Versionen dieser Funktion das vorherige Resultset und Spalten.  Wenn `bBind`**true** ist, umschließt er die neuen Spalten.  
  
 Sie sollten diese Funktion nur aufrufen, wenn Sie mehrere Ergebnisse angegeben haben, indem Sie den `CCommand`*TMultiple\=* Vorlagenparameter `CMultipleResults` fest.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CCommand\-Klasse](../../data/oledb/ccommand-class.md)
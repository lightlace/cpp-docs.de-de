---
title: "AtlTraceErrorRecords"
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
  - "ATL.AtlTraceErrorRecords"
  - "ATL::AtlTraceErrorRecords"
  - "AtlTraceErrorRecords"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AtlTraceErrorRecords-Funktion"
ms.assetid: b83970b3-dc2a-445c-9142-f52218719905
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# AtlTraceErrorRecords
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sichert OLE DB Fehler\-Registerinformation zum Sicherungsgerät, wenn ein Fehler zurückgegeben wird.  
  
## Syntax  
  
```  
  
      inline void AtlTraceErrorRecords(   
   HRESULT hrErr = S_OK    
);  
```  
  
#### Parameter  
 `hErr`  
 \[in\] `HRESULT` zurückgegeben von einer OLE DB\-Consumer\-Vorlagenmemberfunktion.  
  
## Hinweise  
 Wenn `hErr` nicht `S_OK` ist, gibt `AtlTraceErrorRecords` Fehler\-Registerinformation OLE DB zum Sicherungsgerät \(die **Debuggen** Registerkarte des Ausgabefensters oder der Datei\).  Die Fehler\-Registerinformation, die vom Anbieter abgerufen wird, enthält Zeilennummer, Quelle, Beschreibung, Hilfedatei, Kontext und GUID für jeden Fehlerrekordeintrag.  `AtlTraceErrorRecords` sichert diese Informationen nur in Debugbuilds.  Bei Releasebuilds ist ein leerer Stub, out der optimiert ist.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [Makros und globale Funktionen für OLE\-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [CDBErrorInfo\-Klasse](../../data/oledb/cdberrorinfo-class.md)
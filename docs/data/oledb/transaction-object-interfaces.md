---
title: "Transaktionsobjekt-Schnittstellen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Schnittstellen, Liste"
  - "Schnittstellen, OLE DB"
  - "OLE DB-Anbietervorlagen, Objektschnittstelle"
  - "OLE DB-Anbieter, Transaktionsunterstützung"
  - "OLE DB, Schnittstellen"
  - "Transaktionsobjekt-Schnittstellen"
ms.assetid: d2ce99ce-6f7a-4ff9-bc6e-acda3633d5c8
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Transaktionsobjekt-Schnittstellen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das Transaktionsobjekt definiert eine atomare Arbeitseinheit für eine Datenquelle und bestimmt, in welcher Beziehung diese Arbeitseinheiten zueinander stehen.  Dieses Objekt wird von den OLE DB\-Anbietervorlagen nicht direkt unterstützt \(d. h., Sie müssen ein eigenes Objekt erstellen\).  
  
 In der folgenden Tabelle sind die erforderlichen und optionalen Schnittstellen aufgeführt, die in OLE DB für Transaktionsobjekte definiert sind.  
  
|Schnittstelle|Erforderlich?|Durch OLE DB\-Vorlagen implementiert?|  
|-------------------|-------------------|-------------------------------------------|  
|[\<caps:sentence id\="tgt7" sentenceid\="63e99e63156fc90f114fa402662387ef" class\="tgtSentence"\>IConnectionPointContainer\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms683857)|Erforderlich|nein|  
|[\<caps:sentence id\="tgt10" sentenceid\="f5097e646bb93cceb560c38e13953a89" class\="tgtSentence"\>ITransaction\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms723053.aspx)|Erforderlich|nein|  
|[\<caps:sentence id\="tgt13" sentenceid\="130702210bcc45e1afd88b1f2aae1a0b" class\="tgtSentence"\>ISupportErrorInfo\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms715816.aspx)|Optional|nein|  
  
## Siehe auch  
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)
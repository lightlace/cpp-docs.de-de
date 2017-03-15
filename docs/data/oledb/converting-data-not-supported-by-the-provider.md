---
title: "Konvertieren von Daten, die nicht vom Anbieter unterst&#252;tzt werden | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB-Anbietervorlagen, Nicht unterstützte Datentypen"
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Konvertieren von Daten, die nicht vom Anbieter unterst&#252;tzt werden
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn der Consumer einen vom Anbieter nicht unterstützten Datentyp anfordert, wird durch den OLE DB\-Anbietervorlagencode für `IRowsetImpl::GetData` die Datei Msdadc.dll aufgerufen, um den Datentyp umzuwandeln.  
  
 Bei der Implementierung einer Schnittstelle, wie `IRowsetChange`, die die Datenkonvertierung erfordert, kann **Msdaenum.dll** für die Konvertierung aufgerufen werden.  Verwenden Sie `GetData` \(in **Atldb.h** definiert\) als Beispiel.  
  
## Siehe auch  
 [Arbeiten mit OLE DB\-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)
---
title: "Konvertieren von Daten, die nicht vom Anbieter unterst&#252;tzt werden"
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
  - "OLE DB-Anbietervorlagen, Nicht unterstützte Datentypen"
ms.assetid: f495e50f-530a-4fab-ab54-e0c359785845
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Konvertieren von Daten, die nicht vom Anbieter unterst&#252;tzt werden
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn der Consumer einen vom Anbieter nicht unterstützten Datentyp anfordert, wird durch den OLE DB\-Anbietervorlagencode für `IRowsetImpl::GetData` die Datei Msdadc.dll aufgerufen, um den Datentyp umzuwandeln.  
  
 Bei der Implementierung einer Schnittstelle, wie `IRowsetChange`, die die Datenkonvertierung erfordert, kann **Msdaenum.dll** für die Konvertierung aufgerufen werden.  Verwenden Sie `GetData` \(in **Atldb.h** definiert\) als Beispiel.  
  
## Siehe auch  
 [Arbeiten mit OLE DB\-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)
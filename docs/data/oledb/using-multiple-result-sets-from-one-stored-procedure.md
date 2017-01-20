---
title: "Verwenden mehrerer Resultsets aus einer gespeicherten Prozedur"
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
  - "Mehrere Resultsets"
  - "Gespeicherte Prozeduren, Zurückgeben von Resultsets"
ms.assetid: c450c12c-a76c-4ae4-9675-071a41eeac05
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden mehrerer Resultsets aus einer gespeicherten Prozedur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die meisten gespeicherten Prozeduren geben mehrere Resultsets zurück.  Eine solche gespeicherte Prozedur umfasst gewöhnlich eine oder mehrere **Select**\-Anweisungen.  Der Consumer muss dies beachten, um alle Resultsets behandeln zu können.  
  
### So behandeln Sie mehrere Resultsets  
  
1.  Erstellen Sie eine `CCommand`\-Klasse mit `CMultipleResults` als Vorlagenargument und einem Accessor Ihrer Wahl.  Dabei handelt es sich gewöhnlich um einen dynamischen oder manuellen Accessor.  Wenn Sie einen anderen Accessortyp verwenden, ist es eventuell nicht möglich, die Ausgabespalten für jedes Rowset festzulegen.  
  
2.  Führen Sie die gespeicherte Prozedur wie gewohnt aus, und binden Sie die Spalten \(siehe [Abrufen von Daten](../../data/oledb/fetching-data.md)\).  
  
3.  Verwenden Sie die Daten.  
  
4.  Rufen Sie in der `CCommand`\-Klasse **GetNextResult** auf.  Wenn ein anderer Ergebnisrowset verfügbar ist, gibt `GetNextResult` S\_OK zurück. Wenn Sie einen manuellen Accessor verwenden, sollten Sie die Spalten in diesem Fall erneut binden.  Wenn `GetNextResult` einen Fehler zurückgibt, stehen keine weiteren Resultsets zur Verfügung.  
  
## Siehe auch  
 [Verwenden von gespeicherten Prozeduren](../../data/oledb/using-stored-procedures.md)
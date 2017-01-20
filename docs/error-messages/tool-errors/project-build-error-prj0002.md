---
title: "Projektbuildfehler PRJ0002"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0002"
ms.assetid: 1c820b1f-9a24-4681-80ed-4fcbfd7caa00
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Projektbuildfehler PRJ0002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das Fehlerergebnis wurde von der "Befehlszeile" zurückgegeben.  
  
 Der Befehl ***Befehlszeile***, der aus einer Benutzereingabe im Dialogfeld **Eigenschaftenseiten** resultiert, hat einen Fehlercode zurückgegeben. Das Ausgabefenster enthält jedoch keine diesbezüglichen Informationen.  
  
 Wie dieser Fehler beseitigt wird, hängt davon ab, von welchem Tool der Fehler generiert wurde.  Bei MIDL erhalten Sie einen Hinweis auf die mögliche Fehlerursache, wenn **\/o** \(Ausgabe umleiten\) definiert wurde.  
  
 Eine Batchdatei, z. B. ein benutzerdefinierter Buildschritt oder ein Buildereignis, die keine Informationen über Fehlerzustände enthält, könnte auch die Ursache für einen solchen Fehler sein.
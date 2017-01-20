---
title: "Befehlsobjekt-Schnittstellen"
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
  - "Befehlsobjekt-Schnittstellen [C++]"
  - "Befehlsobjekte [OLE DB]"
  - "OLE DB [C++], Befehlsobjekt-Schnittstellen"
ms.assetid: dacff5ae-252c-4f20-9ad7-4e602cc48536
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Befehlsobjekt-Schnittstellen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das Befehlsobjekt verwendet die `IAccessor`\-Schnittstelle, um Parameterbindungen festzulegen.  Der Consumer ruft `IAccessor::CreateAccessor` auf und übergibt ein Array von `DBBINDING`\-Strukturen.  `DBBINDING` enthält Informationen zu den Spaltenbindungen \(wie Typ und Länge\).  Der Anbieter empfängt die Strukturen und entscheidet, auf welche Weise die Daten übertragen werden und ob Konvertierungen notwendig sind.  
  
 Die `ICommandText`\-Schnittstelle bietet die Möglichkeit, einen Textbefehl anzugeben.  Die `ICommandProperties`\-Schnittstelle ist für die Verwaltung sämtlicher Befehlseigenschaften zuständig.  
  
## Siehe auch  
 [Architektur von OLE DB\-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)
---
title: "Oracle-Verbindungen"
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
  - "Verbindungen [C++], Datenbanken"
  - "Datenbankverbindungen [C++], Oracle"
  - "Datenbanken [C++], Verbinden mit"
  - "Oracle [C++], Erstellen von Verbindungen"
  - "Oracle-Datenbanken [C++]"
  - "Oracle-Datenbanken [C++], Verbindungen"
ms.assetid: d317e763-44aa-47c9-abe8-261d513d894f
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Oracle-Verbindungen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bei der Konfiguration eines Oracle ODBC\-DSNs oder einer OLE DB\-Verbindung müssen die clientseitigen SQL\*Net\-Komponenten von Oracle installiert sein.  Bei SQL\*Net handelt es sich um die Netzwerktransportschicht von Oracle.  Die meisten Oracle ODBC\-Treiber, einschließlich des Microsoft\-Treibers und der OLE DB Oracle\-Anbieterzuordnung von Microsoft, kommunizieren direkt über diese SQL\*Net\-Schicht.  
  
 Notieren Sie nach der Konfiguration von SQL\*Net die SQL\*Net\-Verbindungszeichenfolge.  Sie besteht normalerweise aus einem Bezeichner für den Oracle\-Datenbankservernamen sowie aus dem Netzwerkprotokolltyp \(z. B. TCP\/IP und Named Pipes\).  Die SQL\*Net\-Verbindungszeichenfolge ist häufig einem Alias zugeordnet.  In diesem Fall müssen Sie nur den Alias kennen.  Weitere Informationen zur Konfiguration von SQL\*Net erhalten Sie von Ihrem Oracle\-Datenbankadministrator oder in der SQL\*Net\-Dokumentation. Ein Beispiel für eine Verbindungszeichenfolge finden Sie in der Hilfedatei des Oracle ODBC\-Treibers.  
  
## Siehe auch  
 [Erstellen von Datenbankverbindungen](../../data/ado-rdo/creating-database-connections.md)
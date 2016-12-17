---
title: "Kataloginformationen (MFC-Datenzugriff)"
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
  - "Kataloginformationsdatenbank [C++]"
  - "DAO [C++], Kataloginformationen"
  - "Datenbanken [C++], Kataloginformationsdatenbank"
  - "ODBC [C++], Kataloginformationen"
  - "Tabellen [C++]"
  - "Tabellen [C++], Kataloginformationen"
ms.assetid: c184e80f-ff17-409f-9df8-05275080bb8d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Kataloginformationen (MFC-Datenzugriff)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Informationen zu den Tabellen in einer Datenquelle können die Namen der Tabellen und die darin enthaltenen Spalten, Tabellenberechtigungen, Namen von Primär\- und Fremdschlüsseln, Informationen zu vordefinierten Abfragen oder gespeicherten Prozeduren, Informationen zu Indizes in Tabellen sowie statistische Angaben zu Tabellen umfassen.  
  
 Weitere Informationen finden Sie unter [Datenquelle: Bestimmen des Schemas der Datenquelle \(ODBC\)](../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md).  
  
> [!NOTE]
>  In den DAO\-Klassen von MFC können Sie Kataloginformationen wie folgt abrufen: Verwenden Sie [CDaoDatabase::GetTableDefCount](../Topic/CDaoDatabase::GetTableDefCount.md) und [CDaoDatabase::GetTableDefInfo](../Topic/CDaoDatabase::GetTableDefInfo.md), um die Tabellen in der Datenbank aufzulisten und Informationen für jede Tabelle in einer [CDaoTableDefInfo](../mfc/reference/cdaotabledefinfo-structure.md)\-Struktur zu erhalten.  
  
## Siehe auch  
 [Datenzugriffsprogrammierung \(MFC\/ATL\)](../data/data-access-programming-mfc-atl.md)
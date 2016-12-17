---
title: "ODBC und die Datenbankklassen"
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
  - "Datenbankklassen [C++], ODBC"
  - "MFC [C++], ODBC und"
  - "ODBC-API-Funktionen [C++]"
  - "ODBC-Klassen [C++], MFC-Datenbankklassen"
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# ODBC und die Datenbankklassen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die MFC\-ODBC\-Datenbankklassen schließen die ODBC\-API\-Funktionsaufrufe ein, die normalerweise durch die [CDatabase](../../mfc/reference/cdatabase-class.md)\-Memberfunktion und die [CRecordset](../../mfc/reference/crecordset-class.md)\-Memberfunktion durchgeführt werden.  Die Datenbankklassen verwalten z. B. die komplexen ODBC\-Aufrufsequenzen, das Binden der zurückgelieferten Datensätze an Speicherpositionen, das Behandeln von Fehlerzuständen und einige weitere Operationen.  Sie können daher auf eine wesentlich einfachere Klassenschnittstelle zugreifen, um Datensätze über ein Recordset\-Objekt zu ändern.  
  
> [!NOTE]
>  Auf ODBC\-Datenquellen können Sie über die MFC\-ODBC\-Klassen zugreifen, wie in diesem Thema beschrieben, oder über die MFC\-Datenzugriffsobjekt\-Klassen \(DAO\-Klassen\).  
  
 Auch wenn die Datenbankklassen ODBC\-Funktionalität einschließen, bieten sie wesentlich mehr als eine einfache Zuordnung der ODBC\-API\-Funktionen.  Die Datenbankklassen stellen eine höhere Abstraktionsebene zur Verfügung, die den Datenzugriffsobjekten von Microsoft Access und Microsoft Visual Basic nachgebildet ist.  Weitere Informationen finden Sie unter [Wie ist das MFC\-Modell für die Datenbankprogrammierung aufgebaut?](../../data/what-is-the-mfc-database-programming-model-q.md)  
  
## Siehe auch  
 [Grundlagen zu ODBC](../../data/odbc/odbc-basics.md)
---
title: "Befehlshandler f&#252;r das Scrollen von Datens&#228;tzen (MFC-Datenzugriff) | Microsoft Docs"
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
  - "Datensatzscrollen [C++]"
  - "Datensatzansichten [C++], Scrollen"
  - "Scrollen von Datensätzen"
ms.assetid: f8b13477-2a37-459e-a30c-806fb78165ac
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Befehlshandler f&#252;r das Scrollen von Datens&#228;tzen (MFC-Datenzugriff)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Klassen [CRecordView](../mfc/reference/crecordview-class.md) und [CDaoRecordView](../mfc/reference/cdaorecordview-class.md) bieten die Standardbefehlsbehandlung für die folgenden Standardbefehle:  
  
-   **ID\_RECORD\_MOVE\_FIRST**  
  
-   **ID\_RECORD\_MOVE\_LAST**  
  
-   **ID\_RECORD\_MOVE\_NEXT**  
  
-   **ID\_RECORD\_MOVE\_PREV**  
  
 Die `OnMove`\-Memberfunktion der Klassen `CRecordView` und `CDaoRecordView` bietet die Standardbefehlsbehandlung für alle vier Befehle, die von Datensatz zu Datensatz verschoben werden.  Nachdem diese Befehle ausgegeben wurden, lädt RFX \(oder DFX\) den neuen Datensatz in die Recordset\-Felder, und DDX verschiebt die Werte in die Steuerelemente des Datensatzformulars.  Weitere Informationen zu RFX finden Sie unter [Datensatzfeldaustausch \(RFX\)](../data/odbc/record-field-exchange-rfx.md).  
  
> [!NOTE]
>  Verwenden Sie diese Standardbefehls\-IDs für alle Benutzeroberflächenobjekte, die den standardmäßigen Navigationsbefehlen des Datensatzes zugeordnet sind.  
  
## Siehe auch  
 [Navigationsunterstützung in einer Datensatzansicht](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)
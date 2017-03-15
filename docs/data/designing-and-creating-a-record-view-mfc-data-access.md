---
title: "Entwerfen und Erstellen einer Datensatzansicht (MFC-Datenzugriff) | Microsoft Docs"
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
  - "Anwendungsassistenten [C++], Erstellen von Datensatzansichtsklassen"
  - "Entwerfen von Formularen"
  - "Entwerfen von Datensatzansichten"
  - "Formulare [C++], Entwerfen"
  - "Datensatzansichten, Erstellen"
  - "Datensatzansichten, Entwerfen"
ms.assetid: 1d6f5439-754f-4b8b-a19d-841a4657827b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Entwerfen und Erstellen einer Datensatzansicht (MFC-Datenzugriff)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können die Datensatzansichtsklasse mit dem [MFC\-Anwendungs\-Assistenten](../mfc/reference/database-support-mfc-application-wizard.md) erstellen.  Wenn Sie einen Anwendungs\-Assistenten verwenden, erstellt er die Datensatzansichtsklasse und eine Dialogfeldvorlagen\-Ressource \(ohne Steuerelemente\).  Sie müssen den Visual C\+\+\-Dialog\-Editor verwenden, um der Dialogfeldvorlagen\-Ressource Steuerelemente hinzuzufügen.  Andererseits müssen Sie bei der Verwendung von **Klasse hinzufügen** zunächst die Dialogfeldvorlagen\-Ressource im Dialogfeld\-Editor und dann die Datensatzansichtsklasse erstellen.  
  
 Diese Informationen gelten sowohl für `CRecordView` als auch `CDaoRecordView`.  
  
#### So erstellen Sie eine Datensatzansicht mit dem MFC\-Anwendungs\-Assistenten  
  
1.  Siehe [Datenbankunterstützung, MFC\-Anwendungs\-Assistent](../mfc/reference/database-support-mfc-application-wizard.md).  
  
#### So entwerfen Sie ein Formular  
  
1.  Siehe [Dialog\-Editor](../mfc/dialog-editor.md).  
  
#### So erstellen Sie eine Datensatzansichtsklasse  
  
1.  Siehe [Hinzufügen eines MFC\-ODBC\-Consumers](../mfc/reference/adding-an-mfc-odbc-consumer.md).  
  
 Die folgenden Themen erläutern die zusätzlichen Informationen zur Verwendung von Datensatzansichten:  
  
-   [Datensatzansichten: Navigationsunterstützung in einer Datensatzansicht](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)  
  
-   [Datensatzansichten: Verwenden einer Datensatzansicht](../data/using-a-record-view-mfc-data-access.md)  
  
-   [Datensatzansichten: Füllen eines Listenfelds aus einem zweiten Recordset](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)  
  
## Siehe auch  
 [Datensatzansichten \(MFC\-Datenzugriff\)](../data/record-views-mfc-data-access.md)   
 [Recordset \(ODBC\)](../data/odbc/recordset-odbc.md)   
 [Liste der ODBC\-Treiber](../data/odbc/odbc-driver-list.md)
---
title: "Erstellen des Anbieters | Microsoft Docs"
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
  - "OLE DB-Anbieter, Erstellen"
ms.assetid: 2506ba8f-010d-4231-aac1-387432f7b6b9
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Erstellen des Anbieters
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

#### So erstellen Sie einen OLE DB\-Anbieter mit dem ATL\-OLE DB\-Anbieter\-Assistenten  
  
1.  Klicken Sie mit der rechten Maustaste auf das Projekt.  
  
2.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Klasse hinzufügen**.  
  
3.  Wählen Sie im Dialogfeld **Klasse hinzufügen** das Symbol **ATL\-OLE DB\-Anbieter** aus, und klicken Sie auf **Öffnen**.  
  
4.  Geben Sie im ATL\-OLE DB\-Anbieter\-Assistenten im Feld **Kurzer Name** einen kurzen Namen für den Anbieter ein.  In den folgenden Themen wird der kurze Name "MyProvider" verwendet, Sie können jedoch auch einen anderen Namen wählen.  Die Einträge in den anderen Namensfeldern werden automatisch an den eingegebenen Namen angepasst.  
  
5.  Bearbeiten Sie ggf. die anderen Namensfelder.  Neben den Objekt\- und Dateinamen können folgende Bezeichnungen bearbeitet werden:  
  
    -   `CoClass`: Der von COM zum Erstellen des Anbieters verwendete Name.  
  
    -   **ProgID**: Der programmgesteuerte Bezeichner, also eine Textzeichenfolge, die anstelle einer GUID verwendet werden kann.  
  
    -   **Version**: Wird in Verbindung mit der Programm\-ID und der Co\-Klasse verwendet, um eine versionsabhängige programmgesteuerte ID zu generieren.  
  
6.  Klicken Sie auf **Fertig stellen**.  
  
## Siehe auch  
 [Erstellen eines OLE DB\-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)
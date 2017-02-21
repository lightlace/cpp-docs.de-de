---
title: "Die CCmdUI-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CCmdUI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCmdUI-Klasse, Menüaktualisierung"
  - "Symbolleisten [C++], Aktualisieren"
  - "Updatehandler"
  - "Aktualisieren von Benutzeroberflächenobjekten"
  - "Benutzerschnittstellenobjekte, Aktualisieren"
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Die CCmdUI-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn es einen Updates\-Befehl zu seinem Handler weiterleitet, besteht das Framework den Handler ein Zeiger auf ein `CCmdUI`\-Objekt bzw. ein Objekt von `CCmdUI` abgeleitete Klasse\).  Dieses Objekt stellt das Menüelement oder die Symbolleisten\-Schaltfläche oder anderes Benutzeroberflächeobjekt dar, die den Befehl generierten.  Die Aktualisierungshandleraufrufsmemberfunktionen der `CCmdUI`\-Struktur durch den Mauszeiger, um den Benutzeroberflächeobjekts zu aktualisieren.  Es folgt ein Aktualisierungshandler für den freien Raum alles Menüelement:  
  
 [!CODE [NVC_MFCDocView#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocView#3)]  
  
 Dieser Handler ruft die **Aktivieren**\-Memberfunktion eines Objekts mit Zugriff auf das Menüelement auf.  **Aktivieren** stellt das Element für die Verwendung zur Verfügung.  
  
## Siehe auch  
 [Gewusst wie: Aktualisieren von Benutzeroberflächenobjekten](../mfc/how-to-update-user-interface-objects.md)
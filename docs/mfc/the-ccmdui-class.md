---
title: "Die CCmdUI-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
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
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Die CCmdUI-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn es einen Updates\-Befehl zu seinem Handler weiterleitet, besteht das Framework den Handler ein Zeiger auf ein `CCmdUI`\-Objekt bzw. ein Objekt von `CCmdUI` abgeleitete Klasse\).  Dieses Objekt stellt das Menüelement oder die Symbolleisten\-Schaltfläche oder anderes Benutzeroberflächeobjekt dar, die den Befehl generierten.  Die Aktualisierungshandleraufrufsmemberfunktionen der `CCmdUI`\-Struktur durch den Mauszeiger, um den Benutzeroberflächeobjekts zu aktualisieren.  Es folgt ein Aktualisierungshandler für den freien Raum alles Menüelement:  
  
 [!CODE [NVC_MFCDocView#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocView#3)]  
  
 Dieser Handler ruft die **Aktivieren**\-Memberfunktion eines Objekts mit Zugriff auf das Menüelement auf.  **Aktivieren** stellt das Element für die Verwendung zur Verfügung.  
  
## Siehe auch  
 [Gewusst wie: Aktualisieren von Benutzeroberflächenobjekten](../mfc/how-to-update-user-interface-objects.md)
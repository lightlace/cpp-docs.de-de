---
title: "CWinApp und der MFC-Anwendungs-Assistent"
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
  - "CWinApp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anwendungsassistenten [C++], und CWinApp"
  - "CWinApp-Klasse, und MFC-Anwendungs-Assistent"
  - "MFC [C++], Assistenten"
ms.assetid: f8ac0491-3302-4e46-981d-0790624eb8a2
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# CWinApp und der MFC-Anwendungs-Assistent
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn es ein Anwendungsskelett erstellt, deklariert der MFC\-Anwendungs\-Assistent eine Anwendungsklasse wird von [CWinApp](../mfc/reference/cwinapp-class.md) abgeleitet.  Der MFC\-Anwendungs\-Assistent auch eine Implementierungsdatei, die die folgenden Elemente enthält:  
  
-   Eine Meldungszuordnung für die Anwendungsklasse.  
  
-   Ein leerer Klassenkonstruktor.  
  
-   Eine Variable, die das und das einzige Objekt der Klasse deklariert.  
  
-   Eine Standardimplementierung der `InitInstance`\-Memberfunktion.  
  
 Die Application\-Klasse wird in die Projektkopfzeilen\- und \-hauptleitungsquelldateien eingefügt.  Die Namen der Klasse und der Dateien, die erstellt werden, basieren auf den Projektnamen, den Sie im MFC\-Anwendungs\-Assistenten stellen.  Die einfachste Möglichkeit, den Code für diese Klassen anzuzeigen erfolgt in [Klassenansicht](assetId:///8d7430a9-3e33-454c-a9e1-a85e3d2db925).  
  
 Die Standardimplementierungen und die Meldungszuordnung, der angegeben wurde, sind für viele Zwecke ausreichend, Sie können sie nach Bedarf ändern.  Das interessantesten dieser Implementierungen ist die Memberfunktion `InitInstance`.  In der Regel fügen Sie Code der skelettartigen Implementierung von `InitInstance` hinzu.  
  
## Siehe auch  
 [CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)   
 [Überschreibbare CWinApp\-Memberfunktionen](../mfc/overridable-cwinapp-member-functions.md)   
 [Spezielle CWinApp\-Dienste](../mfc/special-cwinapp-services.md)
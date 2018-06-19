---
title: CWinApp und der MFC-Anwendungs-Assistent | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CWinApp
dev_langs:
- C++
helpviewer_keywords:
- application wizards [MFC], and CWinApp
- CWinApp class [MFC], and MFC Application Wizard
- MFC, wizards
ms.assetid: f8ac0491-3302-4e46-981d-0790624eb8a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d40f314c7717d2e69b2b4802bf9c2c5468511db5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341260"
---
# <a name="cwinapp-and-the-mfc-application-wizard"></a>CWinApp und der MFC-Anwendungs-Assistent
Bei der Erstellung einer skelettanwendung MFC-Anwendungsassistenten deklariert eine Anwendungsklasse abgeleitet [CWinApp](../mfc/reference/cwinapp-class.md). Die MFC-Anwendungs-Assistent erstellt auch eine Implementierungsdatei, die folgenden Elemente enthält:  
  
-   Einer meldungszuordnung für die Anwendungsklasse.  
  
-   Eine leere Klasse-Konstruktor.  
  
-   Eine Variable, die den und nur ein Objekt der Klasse deklariert.  
  
-   Eine Standardimplementierung von Ihrem `InitInstance` Memberfunktion.  
  
 Die Anwendungsklasse wird im Projektheader und Hauptquelldateien platziert. Die Namen der Klasse und der erstellten Dateien basieren auf den Namen des Projekts, die Sie im MFC-Anwendungs-Assistenten angeben. Die einfachste Möglichkeit zum Anzeigen des Codes für diese Klassen ist über [Klassenansicht](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925).  
  
 Die standardimplementierungen und meldungszuordnung bereitgestellten für viele Zwecke geeignet sind, aber Sie können diese nach Bedarf ändern. Dieser Implementierungen am interessantesten ist die `InitInstance` Memberfunktion. In der Regel fügen Sie Code, für eine skeletal Implementierung der `InitInstance`.  
  
## <a name="see-also"></a>Siehe auch  
 [CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)   
 [Überschreibbare CWinApp-Memberfunktionen](../mfc/overridable-cwinapp-member-functions.md)   
 [Spezielle CWinApp-Dienste](../mfc/special-cwinapp-services.md)


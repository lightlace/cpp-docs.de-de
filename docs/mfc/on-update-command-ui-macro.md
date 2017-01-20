---
title: "ON_UPDATE_COMMAND_UI Macro"
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
  - "ON_UPDATE_COMMAND_UI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Befehlshandlermakros"
  - "ON_UPDATE_COMMAND_UI-Makro"
  - "Updatehandler"
  - "Aktualisieren von Benutzeroberflächenobjekten"
ms.assetid: 3e72b50f-4119-4c82-81cf-6e09b132de05
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# ON_UPDATE_COMMAND_UI Macro
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie das Fenster **Eigenschaften**, um ein Benutzeroberflächeobjekt zu einem BefehlUpdatehandler in einem BefehlZielobjekt herzustellen.  Es schließt automatisch die ID des Benutzeroberflächeobjekts an das Makro `ON_UPDATE_COMMAND_UI` an und erstellt einen Handler im Objekt erstellt, das das Update behandelt.  Weitere Informationen finden Sie unter [Zuordnungs\-Meldungen auf Funktionen](../mfc/reference/mapping-messages-to-functions.md).  
  
 Um beispielsweise einen freien 3D\-Raum zu aktualisieren verwenden aller Befehl im Menü Bearbeiten des Programms, das Fenster **Eigenschaften**, um einem Eintrag in der Meldungszuordnung in der ausgewählten Klasse, einer Funktionsdeklaration für einen BefehlUpdatehandler, der `OnUpdateEditClearAll` in der Klasse aufgerufen wird, und einer leeren Funktionsvorlage in der Implementierungsdatei der Klasse.  Der Funktionsprototyp sieht wie folgt aus:  
  
 [!CODE [NVC_MFCDocView#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocView#2)]  
  
 Wie alle Handler zeigt die Funktion das **afx\_msg**\-Schlüsselwort an.  Wie alle Aktualisierungshandler entlädt sie ein Argument, einen Zeiger auf ein `CCmdUI`\-Objekt.  
  
## Siehe auch  
 [Gewusst wie: Aktualisieren von Benutzeroberflächenobjekten](../mfc/how-to-update-user-interface-objects.md)
---
title: "ON_UPDATE_COMMAND_UI Macro | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
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
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# ON_UPDATE_COMMAND_UI Macro
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie das Fenster **Eigenschaften**, um ein Benutzeroberflächeobjekt zu einem BefehlUpdatehandler in einem BefehlZielobjekt herzustellen.  Es schließt automatisch die ID des Benutzeroberflächeobjekts an das Makro `ON_UPDATE_COMMAND_UI` an und erstellt einen Handler im Objekt erstellt, das das Update behandelt.  Weitere Informationen finden Sie unter [Zuordnungs\-Meldungen auf Funktionen](../mfc/reference/mapping-messages-to-functions.md).  
  
 Um beispielsweise einen freien 3D\-Raum zu aktualisieren verwenden aller Befehl im Menü Bearbeiten des Programms, das Fenster **Eigenschaften**, um einem Eintrag in der Meldungszuordnung in der ausgewählten Klasse, einer Funktionsdeklaration für einen BefehlUpdatehandler, der `OnUpdateEditClearAll` in der Klasse aufgerufen wird, und einer leeren Funktionsvorlage in der Implementierungsdatei der Klasse.  Der Funktionsprototyp sieht wie folgt aus:  
  
 [!CODE [NVC_MFCDocView#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocView#2)]  
  
 Wie alle Handler zeigt die Funktion das **afx\_msg**\-Schlüsselwort an.  Wie alle Aktualisierungshandler entlädt sie ein Argument, einen Zeiger auf ein `CCmdUI`\-Objekt.  
  
## Siehe auch  
 [Gewusst wie: Aktualisieren von Benutzeroberflächenobjekten](../mfc/how-to-update-user-interface-objects.md)
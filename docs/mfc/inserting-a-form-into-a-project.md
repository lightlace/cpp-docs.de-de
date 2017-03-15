---
title: "Einf&#252;gen eines Formulars in ein Projekt | Microsoft Docs"
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
  - "Formulare, Hinzufügen zu Projekten"
  - "Insert New-Dialogfeld"
  - "Einfügen von"
ms.assetid: f3bd2998-3ce2-496d-ac5c-57ca70eec7cb
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Einf&#252;gen eines Formulars in ein Projekt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Formulare erstellen einen zweckmäßigen Container für Steuerelemente bereit.  Sie können ein MFC\-basiertes Formular in die Anwendung leicht einfügen, wie die Anwendung die MFC\-Bibliotheken unterstützt.  
  
### So konfigurieren Sie ein Formular in Ihr Projekt einfügen  
  
1.  In der Klassenansicht auf das Projekt, dem Sie das Formular hinzufügen möchten, und klicken Sie mit der rechten Maustaste.  
  
2.  Klicken Sie im Kontextmenü zunächst auf **Hinzufügen** und dann auf **Klasse hinzufügen**.  
  
     Wenn der Befehl **Neues Formular** nicht verfügbar ist, ist möglicherweise das Projekt auf Grundlage Active Template Library \(ATL\).  So ein Formular einem ATL\-Projekt hinzufügen, müssen Sie [geben Sie bestimmte Einstellungen an](../atl/reference/application-settings-atl-project-wizard.md), wenn Sie das Projekt erstellen.  
  
3.  Wählen Sie im Ordner **MFC** auf **MFC\-Klasse**.  
  
4.  Mit dem MFC\-Klassen\-Assistenten können Sie die neue Klasse von [CFormView](../mfc/reference/cformview-class.md) ableiten.  
  
 Visual C\+\+ wird das Formular der Anwendung hinzu und öffnet es innerhalb des Dialog\-Editors, damit Sie beginnen, Steuerelemente hinzufügen und auf den Gesamtentwurf Arbeiten.  
  
 Sie sollten die folgenden zusätzlichen Schritte ausführen \(nicht anwendbar für auf Dialogfeldern basierende Anwendungen\):  
  
1.  Überschreiben Sie die `OnUpdate`\-Memberfunktion.  
  
2.  Implementieren Sie eine Memberfunktion, um Daten von der Ansicht in das Dokument zu verschieben.  
  
3.  Erstellen Sie eine `OnPrint`\-Memberfunktion.  
  
## Siehe auch  
 [Formularansichten](../mfc/form-views-mfc.md)
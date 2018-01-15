---
title: "Einfügen eines Formulars in einem Projekt | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- inserting forms [MFC]
- Insert New dialog box [MFC]
- forms, adding to projects
ms.assetid: f3bd2998-3ce2-496d-ac5c-57ca70eec7cb
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 968c24a4f64b88be6de95f0f1dd98c09eb494a97
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="inserting-a-form-into-a-project"></a>Einfügen eines Formulars in ein Projekt
Formulare stellen einen geeigneten Container für Steuerelemente bereit. Solange die Anwendung die MFC-Bibliotheken unterstützt, können Sie problemlos ein MFC-basiertes Formular in Ihrer Anwendung einfügen.  
  
### <a name="to-insert-a-form-into-your-project"></a>So fügen Sie Ihrem Projekt ein Formular  
  
1.  Klassenansicht wählen Sie das Projekt, das Sie das Formular hinzufügen möchten, und klicken Sie auf der rechten Maustaste.  
  
2.  Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Klasse hinzufügen**.  
  
     Wenn die **Formulars** Befehl ist nicht verfügbar, die Ihr Projekt basiert möglicherweise auf die Active Template Library (ATL). Um einem Formular ein ATL-Projekt hinzugefügt haben, müssen Sie [Geben Sie bestimmte Einstellungen](../atl/reference/application-settings-atl-project-wizard.md) beim ersten Erstellen des Projekts.  
  
3.  Aus der **MFC** Ordner, klicken Sie auf **MFC-Klasse**.  
  
4.  Mit der MFC-Klassen-Assistenten legen Sie die neue Klasse, die abgeleitet sein [CFormView](../mfc/reference/cformview-class.md).  
  
 Visual C++ fügt das Formular an Ihre Anwendung innerhalb des Dialog-Editors öffnen, damit Sie beginnen können, Hinzufügen von Steuerelementen und auf dessen Gesamtentwurf arbeiten.  
  
 Möglicherweise möchten die folgenden zusätzlichen Schritte (gilt nicht für Dialogfeld-basierte Anwendungen) ausführen:  
  
1.  Überschreiben Sie die `OnUpdate` Memberfunktion.  
  
2.  Implementieren Sie eine Memberfunktion zum Verschieben von Daten aus der Ansicht in Ihr Dokument.  
  
3.  Erstellen einer `OnPrint` Memberfunktion.  
  
## <a name="see-also"></a>Siehe auch  
 [Formularansichten](../mfc/form-views-mfc.md)


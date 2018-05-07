---
title: Einfügen eines Formulars in einem Projekt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inserting forms [MFC]
- Insert New dialog box [MFC]
- forms, adding to projects
ms.assetid: f3bd2998-3ce2-496d-ac5c-57ca70eec7cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e62618301e09ad4c44fb91608976ecab972a59da
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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


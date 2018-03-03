---
title: Bilden von Ansichten (MFC) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- user interfaces [MFC], forms
- forms [MFC]
- applications [MFC], forms-based
- forms-based applications [MFC]
- forms [MFC], adding to applications
ms.assetid: efbe73c1-4ca4-4613-aac2-30d916e92c0e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4e784858c17c01c8a538edebdb15a89863d16438
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="form-views-mfc"></a>Formularansichten (MFC)
Sie können jede Visual C++-Anwendung, die MFC-Bibliotheken, einschließlich unterstützt, Forms hinzufügen eine [formularbasierte Anwendung](../mfc/reference/creating-a-forms-based-mfc-application.md) (eine, deren View-Klasse abgeleitet ist `CFormView`). Wenn Sie Ihre Anwendung zur Unterstützung Forms anfänglich keine erstellt haben, wird Visual C++ diese Unterstützung für die Sie hinzufügen, wenn Sie ein neues Formular einfügen. In einer SDI- oder MDI-Anwendung, die standardmäßig implementiert [Dokument-/Ansichtsarchitektur](../mfc/document-view-architecture.md), wenn der Benutzer wählt die `New` Befehl (standardmäßig auf die **Datei** Menü), Visual C++ fordert den Benutzer auf Wählen Sie aus den verfügbaren Formen.  
  
 Mit einer SDI-Anwendung, wenn der Benutzer wählt die `New` Befehl, die aktuelle Instanz des Formulars wird weiterhin ausgeführt, aber eine neue Instanz der Anwendung durch das ausgewählte Formular wird erstellt, wenn eine nicht gefunden wird. Die aktuelle Instanz des Formulars in ein MDI-Anwendung weiterhin ausgeführt werden, wenn der Benutzer wählt die `New` Befehl.  
  
> [!NOTE]
>  Sie können ein Formular in eine auf Dialogfeldern basierende Anwendung einfügen (, deren Dialogfeldklasse basiert auf, einem `CDialog` und eine der in der Ansicht keine Klasse implementiert ist). Allerdings ohne die Dokument-/Ansichtarchitektur Visual C++ automatisch implementiert nicht die **Datei**&#124; **Neue** Funktionalität. Sie müssen eine Möglichkeit für den Benutzer so zeigen Sie weitere Formen wie z. B. ein Dialogfeld im Registerformat mit verschiedenen Eigenschaftenseiten implementieren erstellen.  
  
 Wenn Sie ein neues Formular in Ihrer Anwendung einfügen, führt Visual C++ Folgendes aus:  
  
-   Erstellt eine Klasse, die basierend auf einer Formatvorlage Klassen, die Sie auswählen (`CFormView`, `CRecordView`, `CDaoRecordView`, oder `CDialog`).  
  
-   Erstellt eine Dialogfeldressource mit entsprechenden Stile (oder Sie können eine vorhandenen Dialog-Ressource, die noch keiner Klasse zugeordnet wurde).  
  
     Wenn Sie eine bestehende Dialogfeldressource auswählen, müssen Sie diese Formate mithilfe der Seite "Eigenschaften" für das Dialogfeld festgelegt. Formate für ein Dialogfeld müssen enthalten:  
  
     **WS_CHILD**= On  
  
     `WS_BORDER`= Off  
  
     **WS_VISIBLE**= Off  
  
     **WS_CAPTION =**deaktivieren  
  
 Für Anwendungen basierend auf der Dokument-/Ansichtarchitektur den **Formulars** Befehl (in der Klassenansicht durch Rechtsklicken) auch:  
  
-   Erstellt eine **CDocument**-basierten Klasse  
  
     Anstatt eine neue Klasse erstellt haben, können Sie alle vorhandenen **CDocument**-basierten Klasse in Ihrem Projekt.  
  
-   Generiert eine Dokumentvorlage (abgeleitet von **CDocument**) mit Zeichenfolgen-, Menüs und Symbol für Ressourcen.  
  
     Sie können auch eine neue Klasse für die Grundlage für die Vorlage erstellen.  
  
-   Fügt einen Aufruf von **AddDocumentTemplate zum** in Ihrer Anwendungsverzeichnis `InitInstance` Code.  
  
     Visual C++ fügt dieser Code für jedes neue Formular erstellen, die in der Liste der verfügbaren Formulare des Formulars hinzugefügt, wenn der Benutzer wählt die `New` Befehl. Dieser Code umfasst des Formulars zugeordneten Ressourcen-ID und die Namen der zugeordneten Dokument, Ansicht und Frameklassen, die zusammen die neue Form-Objekt bilden.  
  
     Dokumentvorlagen dienen als Verbindung zwischen Dokumenten, Rahmenfenstern und Ansichten. Für ein einzelnes Dokument können Sie viele Vorlagen erstellen.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Erstellen Sie eine formularbasierte Anwendung](../mfc/reference/creating-a-forms-based-mfc-application.md)  
  
-   [Einfügen eines Formulars in ein Projekt](../mfc/inserting-a-form-into-a-project.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Benutzeroberflächenelemente](../mfc/user-interface-elements-mfc.md)

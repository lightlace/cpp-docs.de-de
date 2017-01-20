---
title: "Hinzuf&#252;gen einer MFC-Klasse aus einer Typbibliothek"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Klassen [C++], Hinzufügen von MFC"
  - "MFC, Hinzufügen von Klassen aus Typbibliotheken"
  - "Typbibliotheken, Hinzufügen von MFC-Klassen aus"
ms.assetid: aba40476-3cfb-47af-990e-ae2e9e0d79cf
caps.latest.revision: 13
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Hinzuf&#252;gen einer MFC-Klasse aus einer Typbibliothek
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit diesem Assistenten können Sie eine MFC\-Klasse erstellen, indem Sie eine Schnittstelle aus einer verfügbaren Typbibliothek verwenden.  MFC\-Klassen können einer [MFC\-Anwendung](../../mfc/reference/creating-an-mfc-application.md), einer [MFC\-DLL](../../mfc/reference/creating-an-mfc-dll-project.md) oder einem [MFC\-ActiveX\-Steuerelement](../../mfc/reference/creating-an-mfc-activex-control.md) hinzugefügt werden.  
  
> [!NOTE]
>  Damit eine Klasse aus einer Typbibliothek hinzugefügt werden kann, ist es nicht erforderlich, das MFC\-Projekt mit integrierter Automatisierungsunterstützung zu erstellen.  
  
 Eine Typbibliothek enthält eine binäre Beschreibung der von einer Komponente zur Verfügung gestellten Schnittstellen. In der Bibliothek sind die Methoden zusammen mit ihren Parametern und Rückgabetypen definiert.  Die Typbibliothek muss registriert sein, damit sie im Assistenten zum Hinzufügen von Klassen aus der Typbibliothek im Dialogfeld "Klasse hinzufügen" in der Liste **Verfügbare Typbibliotheken** aufgeführt wird.  Weitere Informationen finden Sie in der MSDN Library unter "Inside Distributed COM: Type Libraries and Language Integration".  
  
### So fügen Sie eine MFC\-Klasse aus einer Typbibliothek hinzu  
  
1.  Klicken Sie im **Projektmappen\-Explorer** oder in der [Klassenansicht](assetId:///8d7430a9-3e33-454c-a9e1-a85e3d2db925) mit der rechten Maustaste auf den Namen des Projekts, dem Sie die Klasse hinzufügen möchten.  
  
2.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Klasse hinzufügen**.  
  
3.  Klicken Sie im Bereich "Vorlagen" des Dialogfelds [Klasse hinzufügen](../../ide/add-class-dialog-box.md) zunächst auf **MFC\-Klasse aus der Typbibliothek \(typelib\)** und dann auf **Öffnen**, um den [Assistenten zum Hinzufügen von Klassen aus der Typbibliothek](../../mfc/reference/add-class-from-typelib-wizard.md) aufzurufen.  
  
 Im Assistenten können Sie innerhalb einer Typbibliothek mehr als eine Klasse hinzufügen.  Entsprechend können in einer einzelnen Assistentensitzung Klassen aus mehr als einer Typbibliothek hinzugefügt werden.  
  
 Der Assistent erstellt für jede Schnittstelle, die von der ausgewählten Typbibliothek hinzugefügt wird, eine von [COleDispatchDriver](../../mfc/reference/coledispatchdriver-class.md) abgeleitete MFC\-Klasse.  `COleDispatchDriver` implementiert die Clientseite der OLE\-Automatisierung.  
  
## Siehe auch  
 [Automatisierungsclients](../../mfc/automation-clients.md)   
 [Automatisierungsclients: Verwenden von Typbibliotheken](../../mfc/automation-clients-using-type-libraries.md)
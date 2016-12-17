---
title: "Hinzuf&#252;gen einer Klasse aus einem ActiveX-Steuerelement (Visual C++)"
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
  - "ActiveX-Steuerelemente [C++], Hinzufügen von Klassen"
  - "Klassen [C++], Erstellen"
ms.assetid: 729fcb37-54b8-44d5-9b4e-50bb16e0eea4
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Hinzuf&#252;gen einer Klasse aus einem ActiveX-Steuerelement (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit diesem Assistenten können Sie eine MFC\-Klasse von einer Schnittstelle in einem verfügbaren ActiveX\-Steuerelement erstellen.  MFC\-Klassen können einer [MFC\-Anwendung](../mfc/reference/creating-an-mfc-application.md), einer [MFC\-DLL](../mfc/reference/creating-an-mfc-dll-project.md) oder einem [MFC\-ActiveX\-Steuerelement](../mfc/reference/creating-an-mfc-activex-control.md) hinzugefügt werden.  
  
> [!NOTE]
>  Damit eine Klasse aus einem ActiveX\-Steuerelement hinzugefügt werden kann, ist es nicht erforderlich, das MFC\-Projekt mit aktivierter Automatisierungsunterstützung zu erstellen.  
  
 Ein ActiveX\-Steuerelement ist eine wiederverwendbare Softwarekomponente, die auf dem Component Object Model \(COM\) basiert. Dieses Modell unterstützt zahlreiche OLE\-Funktionen und kann an die unterschiedlichsten Softwareanforderungen angepasst werden.  ActiveX\-Steuerelemente sind sowohl für den herkömmlichen Einsatz in ActiveX\-Steuerelementcontainern als auch für die Verwendung in World Wide Web\-Seiten im Internet geeignet.  
  
### So fügen Sie eine MFC\-Klasse aus einem ActiveX\-Steuerelement hinzu  
  
1.  Klicken Sie entweder im **Projektmappen\-Explorer** oder in der [Klassenansicht](assetId:///8d7430a9-3e33-454c-a9e1-a85e3d2db925) mit der rechten Maustaste auf den Namen des Projekts, dem Sie die ActiveX\-Steuerelementklasse hinzufügen möchten.  
  
2.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Klasse hinzufügen**.  
  
3.  Klicken Sie im Dialogfeld [Klasse hinzufügen](../ide/add-class-dialog-box.md) im Bereich "Vorlagen" zunächst auf **MFC\-Klasse von ActiveX\-Steuerelement** und dann auf **Öffnen**, um den [Assistenten zum Hinzufügen von Klassen aus ActiveX\-Steuerelementen](../ide/add-class-from-activex-control-wizard.md) aufzurufen.  
  
 Im Assistenten können Sie mehr als eine Schnittstelle aus einem ActiveX\-Steuerelement hinzufügen.  Ebenso können Sie in einer einzelnen Assistentensitzung Klassen aus mehr als einem ActiveX\-Steuerelement erstellen.  
  
 Klassen können aus ActiveX\-Steuerelementen hinzugefügt werden, die entweder im System registriert oder in Typbibliotheksdateien \(.tlb, .olb, .dll, .ocx, or .exe\) enthalten sind. Letztere müssen nicht im System registriert sein.  Weitere Informationen zum Registrieren von ActiveX\-Steuerelementen finden Sie unter [Registrierung von OLE\-Steuerelementen](../mfc/reference/registering-ole-controls.md).  
  
 Für jede Schnittstelle, die Sie aus dem ausgewählten ActiveX\-Steuerelement hinzufügen, erstellt der Assistent eine aus [CWnd](../mfc/reference/cwnd-class.md) oder [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md) abgeleitete MFC\-Klasse.  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [Introduction to COM and ATL](../atl/introduction-to-com-and-atl.md)
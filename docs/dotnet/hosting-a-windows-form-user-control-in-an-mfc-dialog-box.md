---
title: "Hosten eines Windows Form-Benutzersteuerelements in einem MFC-Dialogfeld | Microsoft Docs"
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
  - "Hosten eines Windows Forms-Steuerelements [C++]"
  - "MFC [C++], Windows Forms-Unterstützung"
  - "Windows Forms [C++], MFC-Unterstützung"
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Hosten eines Windows Form-Benutzersteuerelements in einem MFC-Dialogfeld
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC hostet ein Windows Forms\-Steuerelement als besonderen ActiveX\-Steuerelementtyp und kommuniziert mit dem Steuerelement über ActiveX\-Schnittstellen und Eigenschaften sowie Methoden der <xref:System.Windows.Forms.Control>\-Klasse.  Es wird empfohlen, .NET Framework\-Eigenschaften und \-Methoden verwenden, um mit dem Steuerelement zu arbeiten.  
  
 Eine Beispielanwendung, in der Windows Forms angezeigt werden, die mit MFC verwendet werden, finden Sie im Artikel zur [Integration von MFC und Windows Forms](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
> [!NOTE]
>  In der aktuellen Version kann ein `CDialogBar` \-Objekt keine Windows Forms\-Steuerelemente hosten.  
  
## In diesem Abschnitt  
 [Gewusst wie: Erstellen des Benutzersteuerelements und des Hosts in einem Dialogfeld](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)  
  
 [Gewusst wie: DDX\-\/DDV\-Datenbindung mit Windows Forms](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)  
  
 [Gewusst wie: Auffangen von Windows Forms\-Ereignissen aus systemeigenen C\+\+\-Klassen](../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)  
  
## Referenz  
 [CWinFormsControl Class](../mfc/reference/cwinformscontrol-class.md) &#124; [CDialog Class](../mfc/reference/cdialog-class.md) &#124; [CWnd\-Klasse](../mfc/reference/cwnd-class.md) &#124; <xref:System.Windows.Forms.Control>  
  
## Siehe auch  
 [Verwenden eines Windows Form\-Benutzersteuerelements in MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [Unterschiede beim Programmieren mit Windows Forms und MFC](../dotnet/windows-forms-mfc-programming-differences.md)   
 [Hosten eines Windows Forms\-Benutzersteuerelements als MFC\-Ansicht](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)   
 [Hosten eines Windows Form\-Benutzersteuerelements als MFC\-Dialogfeld](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)
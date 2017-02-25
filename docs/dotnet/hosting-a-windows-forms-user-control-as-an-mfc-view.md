---
title: "Hosten eines Windows Forms-Benutzersteuerelements als MFC-Ansicht | Microsoft Docs"
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
  - "Steuerelemente für Windows Forms [C++], Hosten als MFC-Ansicht"
ms.assetid: 43c02ab4-1366-434c-a980-0b19326d6ea0
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Hosten eines Windows Forms-Benutzersteuerelements als MFC-Ansicht
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC verwendet die CWinFormsView\-Klasse, um ein Windows Forms\-Benutzersteuerelement innerhalb einer MFC\-Ansicht zu hosten.  MFC\-Windows Forms\-Ansichten sind ActiveX\-Steuerelemente.  Das Benutzersteuerelement wird als untergeordnete Ansicht der systemeigenen Ansicht gehostet und nimmt den gesamten Clientbereich der systemeigenen Ansicht ein.  
  
 Das Ergebnis ist dem von [CFormView Class](../mfc/reference/cformview-class.md) verwendeten Modell ähnlich.  Daher können Sie vom Windows Forms\-Designer und der Laufzeit profitieren, um umfangreiche formularbasierte Ansichten zu erstellen.  
  
 Da MFC\-Windows Forms\-Ansichten ActiveX\-Steuerelemente sind, haben diese den gleichen `hwnd` wie MFC\-Ansichten nicht.  Sie können zudem nicht als Zeiger auf eine [CView](../mfc/reference/cview-class.md)\-Ansicht übergeben werden.  Verwenden Sie im Allgemeinen .NET\-Framework\-Methoden, um mit Windows Forms\-Ansichten zu arbeiten, und verlassen Sie sich nicht so sehr auf Win32.  
  
 Eine Beispielanwendung, in der Windows Forms angezeigt werden, die mit MFC verwendet werden, finden Sie im Artikel zur [Integration von MFC und Windows Forms](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
## In diesem Abschnitt  
 [Gewusst wie: Erstellen des Benutzersteuerelements und Hosten der MDI\-Ansicht](../dotnet/how-to-create-the-user-control-and-host-mdi-view.md)  
  
 [Gewusst wie: Hinzufügen von Befehlsrouting zum Windows Forms\-Steuerelement](../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)  
  
 [Gewusst wie: Aufrufen von Ereignissen und Methoden des Windows Forms\-Steuerelements](../dotnet/how-to-call-properties-and-methods-of-the-windows-forms-control.md)  
  
## Siehe auch  
 [Verwenden eines Windows Form\-Benutzersteuerelements in MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [Gewusst wie: Erstellen von zusammengesetzten Steuerelementen](../Topic/How%20to:%20Author%20Composite%20Controls.md)
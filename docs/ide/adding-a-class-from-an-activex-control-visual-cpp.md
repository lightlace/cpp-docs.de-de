---
title: Hinzufügen einer Klasse aus einem ActiveX-Steuerelement (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], adding classes
- classes [C++], creating
ms.assetid: 729fcb37-54b8-44d5-9b4e-50bb16e0eea4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 793adf38da33808371a0df71f671c3e29da75326
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="adding-a-class-from-an-activex-control-visual-c"></a>Hinzufügen einer Klasse aus einem ActiveX-Steuerelement (Visual C++)
Verwenden Sie diesen Assistenten zum Erstellen einer MFC-Klasse von einer Schnittstelle in einem verfügbaren ActiveX-Steuerelement. Sie können eine MFC-Klasse zum Hinzufügen ein [MFC-Anwendung](../mfc/reference/creating-an-mfc-application.md), wird eine [MFC-DLL](../mfc/reference/creating-an-mfc-dll-project.md), oder ein [MFC-ActiveX-Steuerelement](../mfc/reference/creating-an-mfc-activex-control.md).  
  
> [!NOTE]
>  Sie müssen nicht zum Erstellen von MFC-Projekt mit Automatisierung aktiviert, um eine Klasse aus einem ActiveX-Steuerelement hinzufügen.  
  
 Ein ActiveX-Steuerelement ist eine wiederverwendbare Softwarekomponente, die auf dem Component Object Model (COM) basiert. Dieses Modell unterstützt zahlreiche OLE-Funktionen und kann an die unterschiedlichsten Softwareanforderungen angepasst werden. ActiveX-Steuerelemente sind für die Verwendung sowohl im normalen ActiveX-Steuerelementcontainer und im Internet im World Wide Web Pages entworfen.  
  
### <a name="to-add-an-mfc-class-from-an-activex-control"></a>So fügen Sie eine MFC-Klasse aus einem ActiveX-Steuerelement hinzu  
  
1.  In beiden **Projektmappen-Explorer** oder [Klassenansicht](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), mit der rechten Maustaste in des Namens des Projekts, dem Sie die ActiveX-Steuerelementklasse hinzufügen möchten.  
  
2.  Klicken Sie im Kontextmenü auf **hinzufügen**, und klicken Sie dann auf **Klasse hinzufügen**.  
  
3.  In der [Klasse hinzufügen](../ide/add-class-dialog-box.md) (Dialogfeld), klicken Sie im Bereich "Vorlagen" klicken Sie auf **MFC-Klasse von ActiveX-Steuerelement**, und klicken Sie dann auf **öffnen** zum Anzeigen der [Klasse hinzufügen von ActiveX Steuern von Assistenten](../ide/add-class-from-activex-control-wizard.md).  
  
 Im Assistenten können Sie mehr als eine Schnittstelle in einem ActiveX-Steuerelement hinzufügen. Ebenso können Sie Klassen aus mehr als ein ActiveX-Steuerelement in einer einzelnen Assistenten-Sitzung erstellen.  
  
 Können Sie Klassen aus ActiveX-Steuerelemente, die in Ihrem System registrierten hinzufügen, oder Sie können Klassen aus ActiveX-Steuerelemente in Typbibliotheksdateien (TLB-Datei, OLB-, DLL, ".ocx" oder .exe) befindet, ohne sie in Ihrem System Registrierung hinzufügen. Finden Sie unter [OLE-Steuerelemente registrieren](../mfc/reference/registering-ole-controls.md) für Weitere Informationen zum Registrieren von ActiveX-Steuerelemente.  
  
 Der Assistent erstellt eine MFC-Klasse abgeleitet [CWnd](../mfc/reference/cwnd-class.md) oder [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md), für jede Schnittstelle, die Sie aus dem ausgewählten ActiveX-Steuerelement hinzufügen.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [Einführung in COM und ATL](../atl/introduction-to-com-and-atl.md)
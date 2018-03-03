---
title: Hosten eines Windows Form Benutzersteuerelements in MFC-Dialogfeld | Microsoft Docs
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
- MFC [C++], Windows Forms support
- hosting Windows Forms control [C++]
- Windows Forms [C++], MFC support
ms.assetid: 9f66ee52-b7cb-4ffd-8306-392a5da990d8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: da8e8a54947b329fe36eea5c80bdc13ba5cdfa74
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="hosting-a-windows-form-user-control-in-an-mfc-dialog-box"></a>Hosten eines Windows Form-Benutzersteuerelements in einem MFC-Dialogfeld
MFC hostet Windows Forms-Steuerelements als eine spezielle Art von ActiveX-Steuerelement und kommuniziert mit dem Steuerelement mithilfe von ActiveX-Schnittstellen, Eigenschaften und Methoden der <xref:System.Windows.Forms.Control> Klasse. Es wird empfohlen, dass Sie .NET Framework-Eigenschaften und Methoden verwenden, um auf das Steuerelement angewendet werden.  
  
 Eine beispielanwendung, die Windows Forms mit MFC verwendet wird, finden Sie unter [MFC und Windows Forms-Integration](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
> [!NOTE]
>  In der aktuellen Version ein `CDialogBar` Objekt kann keine Windows Forms-Steuerelemente hosten.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Erstellen des Benutzersteuerelements und des Hosts in einem Dialogfeld](../dotnet/how-to-create-the-user-control-and-host-in-a-dialog-box.md)  
  
 [Vorgehensweise: DDX-/DDV-Datenbindung in Windows Forms](../dotnet/how-to-do-ddx-ddv-data-binding-with-windows-forms.md)  
  
 [Vorgehensweise: Auffangen von Windows Forms-Ereignissen aus nativen C++-Klassen](../dotnet/how-to-sink-windows-forms-events-from-native-cpp-classes.md)  
  
## <a name="reference"></a>Verweis  
 [CWinFormsControl Klasse](../mfc/reference/cwinformscontrol-class.md) &#124; [CDialog-Klasse](../mfc/reference/cdialog-class.md) &#124; [CWnd-Klasse](../mfc/reference/cwnd-class.md) &#124;<xref:System.Windows.Forms.Control>  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden Sie ein Windows Form-Benutzersteuerelements in MFC](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [Unterschiede beim Programmieren mit Windows Forms und MFC](../dotnet/windows-forms-mfc-programming-differences.md)   
 [Hosten eines Windows Forms-Benutzersteuerelements als MFC-Ansicht](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)   
 [Hosten eines Windows Form-Benutzersteuerelements als MFC-Dialogfeld](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)
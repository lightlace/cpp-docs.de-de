---
title: "Verwenden eines Windows Form-Benutzersteuerelements in MFC | Microsoft Docs"
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
  - "MFC [C++], Windows Forms-Unterstützung"
  - "Interoperabilität [C++], Windows Forms in MFC"
  - "MFC-Interoperabilität [C++]"
  - "Interop [C++], Windows Forms in MFC"
  - "MFC-Interop [C++]"
  - "Windows Forms [C++], MFC-Unterstützung"
ms.assetid: 63fb099b-1dff-469c-9e34-dab52e122fcd
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Verwenden eines Windows Form-Benutzersteuerelements in MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden die MFC-Windows Forms-Unterstützungsklassen, können Sie Windows Forms-Steuerelemente in einer MFC-Anwendung als ein ActiveX-Steuerelement in MFC-Dialogfelder oder Sichten hosten. Darüber hinaus können Windows Forms-Formulare als MFC-Dialogfelder gehostet werden.  
  
 In den folgenden Abschnitten wird beschrieben, wie Sie:  
  
-   Hosten eines Windows Forms-Steuerelements in einem MFC-Dialogfeld.  
  
-   Hosten Sie ein Windows Forms-Benutzersteuerelements als MFC-Ansicht.  
  
-   Hosten eines Windows Forms-Formulars als MFC-Dialogfeld.  
  
> [!NOTE]
>  MFC-Windows Forms-Integration funktioniert nur in Projekten, die dynamisch mit MFC verknüpft (Projekte, in denen AFXDLL definiert ist).  
  
> [!NOTE]
>  Wenn Sie Ihre Anwendung mit einer privaten (geändert) Kopie der MFC-Windows Forms-Schnittstellen-DLL (mfcmifc80.dll) erstellen, kann es nicht im GAC zu installieren, sofern Sie den Microsoft-Schlüssel mit Ihren eigenen Anbieter Schlüssel ersetzen. Weitere Informationen zum Signieren der Assembly, finden Sie unter [Programmieren mit Assemblys](../Topic/Programming%20with%20Assemblies.md) und [Strong Name Assemblies (Assembly Signing) (C++ / CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).  
  
 Beispielanwendungen, die mithilfe von Windows Forms, finden Sie unter [BirthdayPicker-Beispiel: .NET Framework-Ressourcen mit Windows Forms zeigt](assetId:///ac932aed-5502-4667-be29-709bca435317), [Calculator-Beispiel: Windows Forms-Taschenrechner](assetId:///2283b516-3b7e-45f2-80c4-fdcfb366ce25), und [Scribble-Beispiel: MDI-Anwendung zum Zeichnen von](assetId:///f025da3e-659b-4222-b991-554a1b8b2358).  
  
 Ein beispielanwendung, die Windows Forms mit MFC verwendet wird, finden Sie unter [MFC und Windows Forms-Integration](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en).  
  
 Wenn die MFC-Anwendung Windows Forms verwendet, müssen Sie mfcmifc90.dll mit der Anwendung verteilen. Weitere Informationen finden Sie unter [Verteilen der MFC-Bibliothek](../ide/redistributing-the-mfc-library.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Hosten eines Windows Form-Benutzersteuerelements in einem MFC-Dialogfeld](../dotnet/hosting-a-windows-form-user-control-in-an-mfc-dialog-box.md)  
  
 [Hosten eines Windows Forms-Benutzersteuerelements als MFC-Ansicht](../dotnet/hosting-a-windows-forms-user-control-as-an-mfc-view.md)  
  
 [Hosten eines Windows Form-Benutzersteuerelements als MFC-Dialogfeld](../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)  
  
## <a name="reference"></a>Verweis  
 [CWinFormsControl-Klasse](../mfc/reference/cwinformscontrol-class.md)  
  
 [CWinFormsDialog-Klasse](../mfc/reference/cwinformsdialog-class.md)  
  
 [CWinFormsView-Klasse](../mfc/reference/cwinformsview-class.md)  
  
 [ICommandSource-Schnittstelle](../mfc/reference/icommandsource-interface.md)  
  
 [ICommandTarget-Schnittstelle](../mfc/reference/icommandtarget-interface.md)  
  
 [ICommandUI-Schnittstelle](../mfc/reference/icommandui-interface.md)  
  
 [IView--Schnittstelle](../mfc/reference/iview-interface.md)  
  
 [CommandHandler](../Topic/CommandHandler%20Delegate.md)  
  
 [CommandUIHandler](../Topic/CommandUIHandler%20Delegate.md)  
  
 [DDX_ManagedControl](../Topic/DDX_ManagedControl.md)  
  
 [UICheckState](../Topic/UICheckState%20Enumeration.md)  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Windows Forms](../Topic/Windows%20Forms.md)  
  
 [Windows Forms-Steuerelemente](../Topic/Windows%20Forms%20Controls.md)  
  
 [Benutzersteuerelemente von ASP.NET](../Topic/ASP.NET%20User%20Controls.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Elemente der Benutzeroberfläche](../mfc/user-interface-elements-mfc.md)   
 [Formularansichten](../mfc/form-views-mfc.md)
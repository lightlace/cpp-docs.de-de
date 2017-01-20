---
title: "CWinFormsDialog Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CWinFormsDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinFormsDialog class"
  - "MFC [C++], Windows Forms-Unterstützung"
  - "Windows Forms [C++], MFC-Unterstützung"
ms.assetid: e3cec000-a578-448e-b06a-8af256312f61
caps.latest.revision: 26
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# CWinFormsDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Wrapper für eine MFC\-Dialogfeldklasse, die ein Windows Forms\-Benutzersteuerelement hostet.  
  
## Syntax  
  
```  
template <typename TManagedControl>  
class CWinFormsDialog :   
   public CDialog  
```  
  
#### Parameter  
 `TManagedControl`  
 Das in der MFC\-Anwendung angezeigt werden .NET Framework\-Benutzersteuerelement.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CWinFormsDialog::CWinFormsDialog](../Topic/CWinFormsDialog::CWinFormsDialog.md)|Erstellt ein `CWinFormsDialog`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CWinFormsDialog::GetControl](../Topic/CWinFormsDialog::GetControl.md)|Ruft einen Verweis auf das Windows Forms\-Benutzersteuerelement ab.|  
|[CWinFormsDialog::GetControlHandle](../Topic/CWinFormsDialog::GetControlHandle.md)|Ruft ein Fensterhandle das Windows Forms\-Benutzersteuerelement ab.|  
|[CWinFormsDialog::OnInitDialog](../Topic/CWinFormsDialog::OnInitDialog.md)|Initialisiert das MFC\-Dialogfeld durch Erstellen und das Hosten eines Windows Forms\-Benutzersteuerelements dafür.|  
  
### Öffentliche Operatoren  
  
|Name||  
|----------|-|  
|[CWinFormsDialog::operator \-\>](../Topic/CWinFormsDialog::operator%20-%3E.md)|Ersetzt [CWinFormsDialog::GetControl](../Topic/CWinFormsDialog::GetControl.md) in Ausdrücken.|  
|[CWinFormsDialog::operator TManagedControl^](../Topic/CWinFormsDialog::operator%20TManagedControl%5E.md)|Wandelt einen Typ als Verweis auf ein Windows Forms\-Benutzersteuerelement um.|  
  
## Hinweise  
 `CWinFormsDialog` ist ein Wrapper für eine MFC\-Dialogfeldklasse \([CDialog\-Klasse](../../mfc/reference/cdialog-class.md)\) diese Hosts ein Benutzersteuerelement der Windows Forms \(<xref:System.Windows.Forms.UserControl>\).  Dies ermöglicht die Anzeige von .NET Framework\-Steuerelementen in einem modalen oder ohne MFC\-Dialogfeld.  
  
 Weitere Informationen zur Verwendung von Windows Forms, finden Sie unter [Verwenden eines Windows Form\-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md) und [Hosten eines Windows Form\-Benutzersteuerelements als MFC\-Dialogfeld](../../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md).  
  
## Anforderungen  
 **Header:** afxwinforms.h  
  
## Siehe auch  
 <xref:System.Windows.Forms.UserControl?displayProperty=fullName>   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [CWinFormsView Class](../../mfc/reference/cwinformsview-class.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)
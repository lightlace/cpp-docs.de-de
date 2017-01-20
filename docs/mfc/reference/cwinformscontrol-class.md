---
title: "CWinFormsControl Class"
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
  - "CWinFormsControl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinFormsControl class"
  - "MFC [C++], Windows Forms-Unterstützung"
  - "Windows Forms [C++], MFC-Unterstützung"
ms.assetid: 6406dd7b-fb89-4a18-ac3a-c010d6b6289a
caps.latest.revision: 28
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# CWinFormsControl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die grundlegende Funktionalität zum Hosten eines Windows Forms\-Steuerelements.  
  
## Syntax  
  
```  
template<class TManagedControl>  
class CWinFormsControl : public CWnd  
```  
  
#### Parameter  
 `TManagedControl`  
 Ein in der MFC\-Anwendung angezeigt werden, Framework\-WindowsForms\-Steuerelement .NET.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CWinFormsControl::CWinFormsControl](../Topic/CWinFormsControl::CWinFormsControl.md)|Erstellt ein MFC\-Windows Forms\-Steuerelement\-Wrapperobjekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CWinFormsControl::CreateManagedControl](../Topic/CWinFormsControl::CreateManagedControl.md)|Erstellt ein Windows Forms\-Steuerelement in einem MFC\-Container.|  
|[CWinFormsControl::GetControl](../Topic/CWinFormsControl::GetControl.md)|Ruft einen Zeiger auf das Windows Forms\-Steuerelement ab.|  
|[CWinFormsControl::GetControlHandle](../Topic/CWinFormsControl::GetControlHandle.md)|Ruft ein Handle für das Windows Forms\-Steuerelement ab.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CWinFormsControl::operator \-\>](../Topic/CWinFormsControl::operator%20-%3E.md)|Ersetzt [CWinFormsControl::GetControl](../Topic/CWinFormsControl::GetControl.md) in Ausdrücken.|  
|[CWinFormsControl::operator TManagedControl^](../Topic/CWinFormsControl::operator%20TManagedControl%5E.md)|Wandelt einen Typ als Zeiger auf einem Windows Forms\-Steuerelement um.|  
  
## Hinweise  
 Die `CWinFormsControl`\-Klasse stellt die grundlegende Funktionalität zum Hosten eines Windows Forms\-Steuerelements.  
  
 Weitere Informationen zur Verwendung von Windows Forms, finden Sie unter [Verwenden eines Windows Form\-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 das MFC\-Code sollte die Fensterhandles nicht zwischenspeichern \(normalerweise in `m_hWnd`\).  Einige Windows Forms\-Steuerelement\-Eigenschaften erfordern, dass zugrunde liegende Win32 `Window` mithilfe `DestroyWindow` und `CreateWindow` zerstört und neu erstellt wird.  Die MFC\-WindowsForm\-Implementierung behandelt die `Destroy` und `Create`\-Ereignisse der Steuerelemente, die den `m_hWnd`\-Member zu aktualisieren.  
  
> [!NOTE]
>  Windows Forms\-Integration funktioniert nur in Projekten, die dynamisch mit MFC verknüpft sind \(, in AFXDLL definiert ist\).  
  
## Anforderungen  
 **Header:** afxwinforms.h  
  
## Siehe auch  
 [CWinFormsDialog Class](../../mfc/reference/cwinformsdialog-class.md)   
 [CWinFormsView Class](../../mfc/reference/cwinformsview-class.md)
---
title: "CIPAddressCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CIPAddressCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CIPAddressCtrl class"
  - "Allgemeine Steuerelemente, Internet Explorer 4.0"
  - "Internet address edit box"
  - "Internet Explorer 4.0 common controls"
  - "Internet protocol address box"
  - "IP address control"
ms.assetid: 9764d2f4-cb14-4ba8-b799-7f57a55a47c6
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CIPAddressCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität des Windows\-Common IP\-Adressensteuerelements bereit.  
  
## Syntax  
  
```  
class CIPAddressCtrl : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CIPAddressCtrl::CIPAddressCtrl](../Topic/CIPAddressCtrl::CIPAddressCtrl.md)|Erstellt ein `CIPAddressCtrl`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CIPAddressCtrl::ClearAddress](../Topic/CIPAddressCtrl::ClearAddress.md)|Löscht den Inhalt des IP\-Adressensteuerelement.|  
|[CIPAddressCtrl::Create](../Topic/CIPAddressCtrl::Create.md)|Erstellt ein IP\-Adressensteuerelement und fügt es zu einem `CIPAddressCtrl`\-Objekt.|  
|[CIPAddressCtrl::CreateEx](../Topic/CIPAddressCtrl::CreateEx.md)|Erstellt ein IP\-Adressensteuerelement mit den angegebenen Windows\-erweitertenFormaten und fügt es zu einem `CIPAddressCtrl`\-Objekt.|  
|[CIPAddressCtrl::GetAddress](../Topic/CIPAddressCtrl::GetAddress.md)|Ruft die Adressenwerte für alle vier Felder im IP\-Adressensteuerelement ab.|  
|[CIPAddressCtrl::IsBlank](../Topic/CIPAddressCtrl::IsBlank.md)|Bestimmt, ob alle Felder im IP\-Adressensteuerelement leer sind.|  
|[CIPAddressCtrl::SetAddress](../Topic/CIPAddressCtrl::SetAddress.md)|Legt die Adressenwerte für alle vier Felder im IP\-Adressensteuerelement fest.|  
|[CIPAddressCtrl::SetFieldFocus](../Topic/CIPAddressCtrl::SetFieldFocus.md)|Legt den Tastaturfokus auf das angegebene Feld im IP\-Adressensteuerelement fest.|  
|[CIPAddressCtrl::SetFieldRange](../Topic/CIPAddressCtrl::SetFieldRange.md)|Legt den Bereich im angegebenen Feld im IP\-Adressensteuerelement fest.|  
  
## Hinweise  
 Ein IP\-Adressensteuerelement, ein Steuerelement, das einem Bearbeitungssteuerelement ähnelt, ermöglicht Ihnen, eine numerische Adresse im Format des Internetprotokolls \(IP\) einzugeben und zu bearbeiten.  
  
 Dieses Steuerelement \(und daher die `CIPAddressCtrl`\-Klasse\) ist nur für \- Programmen verfügbar, die unter Microsoft Internet Explorer 4,0 und höher ausgeführt werden.  Es sind auch mit zukünftigen Versionen von Windows und Windows NT verfügbar.  
  
 Weitere allgemeine Informationen zum IP\-Adressensteuerelement finden Sie unter [IP\-Adressen\-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb761372) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CIPAddressCtrl`  
  
## Anforderungen  
 **Header:**  afxcmn.h  
  
## Siehe auch  
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)
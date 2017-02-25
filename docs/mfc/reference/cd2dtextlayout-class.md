---
title: "CD2DTextLayout-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CD2DTextLayout"
  - "afxrendertarget/CD2DTextLayout"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DTextLayout-Klasse"
ms.assetid: 724bd13c-f2ef-4e55-a775-8cb04b7b7908
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# CD2DTextLayout-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Wrapper für "IDWriteTextLayout".  
  
## Syntax  
  
```  
class CD2DTextLayout : public CD2DResource;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DTextLayout::CD2DTextLayout](../Topic/CD2DTextLayout::CD2DTextLayout.md)|Erstellt ein CD2DTextLayout\-Objekt.|  
|[CD2DTextLayout::~CD2DTextLayout](../Topic/CD2DTextLayout::~CD2DTextLayout.md)|Der Destruktor.  Wird aufgerufen, wenn ein D2D\-Textlayoutobjekt zerstört wird.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DTextLayout::Create](../Topic/CD2DTextLayout::Create.md)|Erstellt einen CD2DTextLayout.  \(Überschreibt [CD2DResource::Create](../Topic/CD2DResource::Create.md).\)|  
|[CD2DTextLayout::Destroy](../Topic/CD2DTextLayout::Destroy.md)|Zerstört ein CD2DTextLayout\-Objekt.  \(Überschreibt [CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md).\)|  
|[CD2DTextLayout::Get](../Topic/CD2DTextLayout::Get.md)|Gibt die IDWriteTextLayout\-Schnittstelle zurück|  
|[CD2DTextLayout::GetFontFamilyName](../Topic/CD2DTextLayout::GetFontFamilyName.md)|Kopiert den Schriftfamiliennamen des Texts an der angegebenen Position.|  
|[CD2DTextLayout::GetLocaleName](../Topic/CD2DTextLayout::GetLocaleName.md)|Ruft den Gebietsschemanamen des Texts an der angegebenen Position ab.|  
|[CD2DTextLayout::IsValid](../Topic/CD2DTextLayout::IsValid.md)|Überprüft die Ressourcengültigkeit \(Überschreibt [CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md).\)|  
|[CD2DTextLayout::ReCreate](../Topic/CD2DTextLayout::ReCreate.md)|Erstellt ein CD2DTextLayout neu.  \(Überschreibt [CD2DResource::ReCreate](../Topic/CD2DResource::ReCreate.md).\)|  
|[CD2DTextLayout::SetFontFamilyName](../Topic/CD2DTextLayout::SetFontFamilyName.md)|Legt auf NULL endenden Schriftfamiliennamen für Text innerhalb eines angegebenen Textbereichs fest|  
|[CD2DTextLayout::SetLocaleName](../Topic/CD2DTextLayout::SetLocaleName.md)|Legt den Gebietsschemanamen für Text innerhalb eines angegebenen Textbereichs fest|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DTextLayout::operator IDWriteTextLayout\*](../Topic/CD2DTextLayout::operator%20IDWriteTextLayout*.md)|Gibt die IDWriteTextLayout\-Schnittstelle zurück|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DTextLayout::m\_pTextLayout](../Topic/CD2DTextLayout::m_pTextLayout.md)|Ein Zeiger auf ein IDWriteTextLayout.|  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DTextLayout](../../mfc/reference/cd2dtextlayout-class.md)  
  
## Anforderungen  
 **Header:** afxrendertarget.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
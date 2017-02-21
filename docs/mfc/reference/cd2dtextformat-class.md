---
title: "CD2DTextFormat-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxrendertarget/CD2DTextFormat"
  - "CD2DTextFormat"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DTextFormat-Klasse"
ms.assetid: db194cec-9dae-4644-ab84-7c43b7164117
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CD2DTextFormat-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Wrapper für "IDWriteTextFormat".  
  
## Syntax  
  
```  
class CD2DTextFormat : public CD2DResource;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DTextFormat::CD2DTextFormat](../Topic/CD2DTextFormat::CD2DTextFormat.md)|Erstellt ein CD2DTextFormat\-Objekt.|  
|[CD2DTextFormat::~CD2DTextFormat](../Topic/CD2DTextFormat::~CD2DTextFormat.md)|Der Destruktor.  Wird aufgerufen, wenn ein D2D\-Textformatobjekt zerstört wird.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DTextFormat::Create](../Topic/CD2DTextFormat::Create.md)|Erstellt einen CD2DTextFormat.  \(Überschreibt [CD2DResource::Create](../Topic/CD2DResource::Create.md).\)|  
|[CD2DTextFormat::Destroy](../Topic/CD2DTextFormat::Destroy.md)|Zerstört ein CD2DTextFormat\-Objekt.  \(Überschreibt [CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md).\)|  
|[CD2DTextFormat::Get](../Topic/CD2DTextFormat::Get.md)|Gibt die IDWriteTextFormat\-Schnittstelle zurück|  
|[CD2DTextFormat::GetFontFamilyName](../Topic/CD2DTextFormat::GetFontFamilyName.md)|Ruft eine Kopie des Schriftfamiliennamens ab.|  
|[CD2DTextFormat::GetLocaleName](../Topic/CD2DTextFormat::GetLocaleName.md)|Ruft eine Kopie des Gebietsschemanamens ab.|  
|[CD2DTextFormat::IsValid](../Topic/CD2DTextFormat::IsValid.md)|Überprüft die Ressourcengültigkeit \(Überschreibt [CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md).\)|  
|[CD2DTextFormat::ReCreate](../Topic/CD2DTextFormat::ReCreate.md)|Erstellt ein CD2DTextFormat neu.  \(Überschreibt [CD2DResource::ReCreate](../Topic/CD2DResource::ReCreate.md).\)|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DTextFormat::operator IDWriteTextFormat\*](../Topic/CD2DTextFormat::operator%20IDWriteTextFormat*.md)|Gibt die IDWriteTextFormat\-Schnittstelle zurück|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DTextFormat::m\_pTextFormat](../Topic/CD2DTextFormat::m_pTextFormat.md)|Ein Zeiger auf ein IDWriteTextFormat.|  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DTextFormat](../../mfc/reference/cd2dtextformat-class.md)  
  
## Anforderungen  
 **Header:** afxrendertarget.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
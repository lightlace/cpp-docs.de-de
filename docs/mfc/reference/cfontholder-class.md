---
title: "CFontHolder Class"
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
  - "CFontHolder"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFontHolder class"
  - "custom fonts"
  - "Schriftarten, ActiveX-Steuerelemente"
ms.assetid: 728ab472-0c97-440d-889f-1324c6e1b6b8
caps.latest.revision: 19
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CFontHolder Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert die vordefinierte Schriftarteigenschaft und kapselt die Funktionalität eines Windows\-Schriftartobjekts und der `IFont`\-Schnittstelle.  
  
## Syntax  
  
```  
class CFontHolder  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CFontHolder::CFontHolder](../Topic/CFontHolder::CFontHolder.md)|Erstellt ein `CFontHolder`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CFontHolder::GetDisplayString](../Topic/CFontHolder::GetDisplayString.md)|Ruft die Zeichenfolge ab, die im Eigenschaftenbrowser eines Containers angezeigt wird.|  
|[CFontHolder::GetFontDispatch](../Topic/CFontHolder::GetFontDispatch.md)|Gibt die `IDispatch`\-Schnittstelle der Schriftart zurück.|  
|[CFontHolder::GetFontHandle](../Topic/CFontHolder::GetFontHandle.md)|Gibt ein Handle für eine Windows\-Schriftart zurück.|  
|[CFontHolder::InitializeFont](../Topic/CFontHolder::InitializeFont.md)|Initialisiert ein `CFontHolder`\-Objekt.|  
|[CFontHolder::QueryTextMetrics](../Topic/CFontHolder::QueryTextMetrics.md)|Ruft Informationen für die entsprechende Schriftart ab.|  
|[CFontHolder::ReleaseFont](../Topic/CFontHolder::ReleaseFont.md)|Trennt `CFontHolder` das Objekt aus den `IFont` und `IFontNotification`\-Schnittstellen.|  
|[CFontHolder::Select](../Topic/CFontHolder::Select.md)|Wählt eine Schriftartressource in einen Gerätekontext aus.|  
|[CFontHolder::SetFont](../Topic/CFontHolder::SetFont.md)|Schließt das `CFontHolder`\-Objekt einer `IFont`\-Schnittstelle an.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CFontHolder::m\_pFont](../Topic/CFontHolder::m_pFont.md)|Ein Zeiger auf die `CFontHolder``IFont`\-Schnittstelle des Objekts.|  
  
## Hinweise  
 `CFontHolder` hat keine Basisklasse.  
  
 Verwenden Sie diese Klasse, um benutzerdefinierte Schriftarteigenschaften für das Steuerelement zu implementieren.  Informationen zum Erstellen solcher Eigenschaften, finden Sie im Artikel [ActiveX\-Steuerelemente: Verwenden der Schriftarten](../../mfc/mfc-activex-controls-using-fonts.md).  
  
## Vererbungshierarchie  
 `CFontHolder`  
  
## Anforderungen  
 **Header:**  afxctl.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CPropExchange Class](../../mfc/reference/cpropexchange-class.md)
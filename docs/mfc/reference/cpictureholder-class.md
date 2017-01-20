---
title: "CPictureHolder Class"
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
  - "Picture"
  - "CPictureHolder"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Steuerelemente [MFC], OLE"
  - "CPictureHolder class"
  - "OLE-Steuerelemente, Bild"
  - "Picture property"
ms.assetid: a4f59775-704a-41dd-b5bd-2e531c95127a
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CPictureHolder Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert eine Bildeigenschaft, die dem Benutzer ermöglicht, ein Bild im \- Steuerelement anzuzeigen.  
  
## Syntax  
  
```  
class CPictureHolder  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CPictureHolder::CPictureHolder](../Topic/CPictureHolder::CPictureHolder.md)|Erstellt ein `CPictureHolder`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CPictureHolder::CreateEmpty](../Topic/CPictureHolder::CreateEmpty.md)|Erstellt ein leeres `CPictureHolder`\-Objekt.|  
|[CPictureHolder::CreateFromBitmap](../Topic/CPictureHolder::CreateFromBitmap.md)|Erstellt ein Objekt `CPictureHolder` einer Bitmap.|  
|[CPictureHolder::CreateFromIcon](../Topic/CPictureHolder::CreateFromIcon.md)|Erstellt ein Objekt `CPictureHolder` von einem Symbol.|  
|[CPictureHolder::CreateFromMetafile](../Topic/CPictureHolder::CreateFromMetafile.md)|Erstellt ein Objekt aus einer `CPictureHolder` Metadatei.|  
|[CPictureHolder::GetDisplayString](../Topic/CPictureHolder::GetDisplayString.md)|Ruft die Zeichenfolge ab, die im Eigenschaftenbrowser des Steuerelementcontainers angezeigt wird.|  
|[CPictureHolder::GetPictureDispatch](../Topic/CPictureHolder::GetPictureDispatch.md)|Gibt die `CPictureHolder``IDispatch`\-Schnittstelle des Objekts zurück.|  
|[CPictureHolder::GetType](../Topic/CPictureHolder::GetType.md)|Teilt mit, ob das `CPictureHolder`\-Objekt eine Bitmap, ein Symbol oder eine Metadatei ist.|  
|[CPictureHolder::Render](../Topic/CPictureHolder::Render.md)|Gibt das Bild.|  
|[CPictureHolder::SetPictureDispatch](../Topic/CPictureHolder::SetPictureDispatch.md)|Legt die `CPictureHolder``IDispatch`\-Schnittstelle des Objekts fest.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CPictureHolder::m\_pPict](../Topic/CPictureHolder::m_pPict.md)|Ein Zeiger auf ein Bildobjekt.|  
  
## Hinweise  
 `CPictureHolder` hat keine Basisklasse.  
  
 Mit der vordefinierten Bildeigenschaft kann der Entwickler eine Bitmap, ein Symbol oder eine Metadatei für die Anzeige angeben.  
  
 Informationen zum Erstellen benutzerdefinierter Bildeigenschaften, finden Sie im Artikel [MFC\-ActiveX\-Steuerelemente: Verwenden der Bilder in einem ActiveX\-Steuerelement](../../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md).  
  
## Vererbungshierarchie  
 `CPictureHolder`  
  
## Anforderungen  
 **Header:**  afxctl.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFontHolder Class](../../mfc/reference/cfontholder-class.md)
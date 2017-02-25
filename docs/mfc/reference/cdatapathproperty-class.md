---
title: "CDataPathProperty Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDataPathProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Steuerelemente [C++], Asynchron"
  - "asynchronous controls [C++]"
  - "CDataPathProperty class"
  - "OLE-Steuerelemente [C++], Asynchron"
ms.assetid: 1f96efdb-54e4-460b-862c-eba5d4103488
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CDataPathProperty Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert eine OLE\-Steuerelement\-Eigenschaft, die asynchron geladen werden kann.  
  
## Syntax  
  
```  
class CDataPathProperty : public CAsyncMonikerFile  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CDataPathProperty::CDataPathProperty](../Topic/CDataPathProperty::CDataPathProperty.md)|Erstellt ein `CDataPathProperty`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CDataPathProperty::GetControl](../Topic/CDataPathProperty::GetControl.md)|Ruft das asynchrone OLE\-Steuerelement ab, das dem `CDataPathProperty`\-Objekt zugeordnet ist.|  
|[CDataPathProperty::GetPath](../Topic/CDataPathProperty::GetPath.md)|Ruft den Pfadnamen der Eigenschaft ab.|  
|[CDataPathProperty::Open](../Topic/CDataPathProperty::Open.md)|Initiiert Laden der asynchronen Eigenschaft für das zugeordnete Steuerelement ActiveX \(OLE\).|  
|[CDataPathProperty::ResetData](../Topic/CDataPathProperty::ResetData.md)|Ruft `CAsyncMonikerFile::OnDataAvailable` auf, um den Container zu benachrichtigen, dass die Steuerelementeigenschaften geändert haben.|  
|[CDataPathProperty::SetControl](../Topic/CDataPathProperty::SetControl.md)|Legt das asynchrone Steuerelement ActiveX \(OLE\) fest, das der Eigenschaft zugeordnet ist.|  
|[CDataPathProperty::SetPath](../Topic/CDataPathProperty::SetPath.md)|Legt den Pfadnamen der Eigenschaft fest.|  
  
## Hinweise  
 Asynchrone Eigenschaften werden nach synchroner Initiierung geladen.  
  
 Die Klasse `CDataPathProperty` wird von **CAysncMonikerFile** abgeleitet.  Um asynchrone Eigenschaften in den OLE\-Steuerelementen zu implementieren, leiten Sie eine Klasse von `CDataPathProperty`, und überschreiben Sie [OnDataAvailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md).  
  
 Weitere Informationen dazu, wie asynchrone Moniker und ActiveX\-Steuerelemente in Internetanwendungen, finden Sie die folgenden Elemente verwendet:  
  
-   [Internet\-erste Schritte: ActiveX\-Steuerelemente](../../mfc/activex-controls-on-the-internet.md)  
  
-   [Internet\-erste Schritte: Asynchrone Moniker](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Die C\-Datei](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 `CDataPathProperty`  
  
## Anforderungen  
 **Header:** afxctl.h  
  
## Siehe auch  
 [MFC Sampling Bild](../../top/visual-cpp-samples.md)   
 [CAsyncMonikerFile Class](../../mfc/reference/casyncmonikerfile-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CAsyncMonikerFile Class](../../mfc/reference/casyncmonikerfile-class.md)
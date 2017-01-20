---
title: "CSnapInItemImpl Class"
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
  - "CSnapInItemImpl"
  - "ATL.CSnapInItemImpl"
  - "ATL::CSnapInItemImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSnapInItemImpl class"
  - "snap-ins"
  - "snap-ins, ATL support for"
  - "snap-ins, data items"
ms.assetid: 52caefbd-9eae-49b0-add2-d55524271aa7
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CSnapInItemImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Implementieren eines Snap\-Inknotenobjekts bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template <  
class T,  
BOOL bIsExtension= FALSE  
>  
class ATL_NO_VTABLE CSnapInItemImpl :  
public CSnapInItem  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `CSnapInItemImpl`.  
  
 *bIsExtension*  
 **TRUE**, wenn das Objekt eine Snap\-Inerweiterung ist; andernfalls **FALSE**.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSnapInItemImpl::CSnapInItemImpl](../Topic/CSnapInItemImpl::CSnapInItemImpl.md)|Konstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSnapInItemImpl::AddMenuItems](../Topic/CSnapInItemImpl::AddMenuItems.md)|Fügt einem Kontextmenü Menüelemente hinzu.|  
|[CSnapInItemImpl::Command](../Topic/CSnapInItemImpl::Command.md)|Aufgerufen durch die Konsole, wenn ein Element des benutzerdefinierten Menübefehl ausgewählt ist.|  
|[CSnapInItemImpl::CreatePropertyPages](../Topic/CSnapInItemImpl::CreatePropertyPages.md)|Fügt dem Eigenschaftenblatt Seiten des MMC\-Snap\-Ins hinzu.|  
|[CSnapInItemImpl::FillData](../Topic/CSnapInItemImpl::FillData.md)|Kopieninformationen zum Snap\-Inobjekt in einen angegebenen Stream.|  
|[CSnapInItemImpl::GetResultPaneInfo](../Topic/CSnapInItemImpl::GetResultPaneInfo.md)|Ruft die **RESULTDATAITEM**\-Struktur des MMC\-Snap\-Ins ab.|  
|[CSnapInItemImpl::GetResultViewType](../Topic/CSnapInItemImpl::GetResultViewType.md)|Bestimmt den Typ der Ansicht wird von den Ergebnisbereich.|  
|[CSnapInItemImpl::GetScopePaneInfo](../Topic/CSnapInItemImpl::GetScopePaneInfo.md)|Ruft die **SCOPEDATAITEM**\-Struktur des MMC\-Snap\-Ins ab.|  
|[CSnapInItemImpl::Notify](../Topic/CSnapInItemImpl::Notify.md)|Aufgerufen durch die Konsole, um das MMC\-Snap\-In von den Aktionen zu benachrichtigen ergriffen vom Benutzer.|  
|[CSnapInItemImpl::QueryPagesFor](../Topic/CSnapInItemImpl::QueryPagesFor.md)|Aufgerufen, um festzustellen, ob der Snap\-Inknoten Eigenschaftenseiten unterstützt.|  
|[CSnapInItemImpl::SetMenuInsertionFlags](../Topic/CSnapInItemImpl::SetMenuInsertionFlags.md)|Ändert die Menüeinfügungsflags für ein Snap\-Inobjekt.|  
|[CSnapInItemImpl::SetToolbarButtonInfo](../Topic/CSnapInItemImpl::SetToolbarButtonInfo.md)|Legt die Informationen der angegebenen Symbolleisten\-Schaltfläche fest.|  
|[CSnapInItemImpl::UpdateMenuState](../Topic/CSnapInItemImpl::UpdateMenuState.md)|Aktualisiert den Zustand eines Kontextmenüelements.|  
|[CSnapInItemImpl::UpdateToolbarButton](../Topic/CSnapInItemImpl::UpdateToolbarButton.md)|Aktualisiert den Zustand der angegebenen Symbolleistenschaltfläche.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CSnapInItemImpl::m\_bstrDisplayName](../Topic/CSnapInItemImpl::m_bstrDisplayName.md)|Der Name des Snap\-Inobjekts.|  
|[CSnapInItemImpl::m\_resultDataItem](../Topic/CSnapInItemImpl::m_resultDataItem.md)|Die Struktur Windows **RESULTDATAITEM** wird vom `CSnapInItemImpl`\-Objekt.|  
|[CSnapInItemImpl::m\_scopeDataItem](../Topic/CSnapInItemImpl::m_scopeDataItem.md)|Die Struktur Windows **SCOPEDATAITEM** wird vom `CSnapInItemImpl`\-Objekt.|  
  
## Hinweise  
 `CSnapInItemImpl` stellt eine grundlegende Implementierung für ein Snap\-Inknotenobjekt, wie das Hinzufügen von Menüelementen und Symbolleisten und Weiterleiten von Befehlen für den Snap\-Inknoten der entsprechenden Handlerfunktion bereit.  Diese Funktionen werden mit einer Reihe verschiedener Schnittstellen implementiert und Typen zuordnen.  Die Standardimplementierungshandlebenachrichtigungen an den Knotenobjekt durch das Bestimmen der richtigen Instanz der abgeleiteten Klasse und die Nachricht weiterleitet zur richtigen Instanz.  
  
## Vererbungshierarchie  
 `CSnapInItem`  
  
 `CSnapInItemImpl`  
  
## Anforderungen  
 **Header:**  atlsnap.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)
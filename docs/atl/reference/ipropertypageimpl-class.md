---
title: "IPropertyPageImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IPropertyPageImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPropertyPage ATL implementation"
  - "IPropertyPageImpl class"
  - "Eigenschaftenseiten"
ms.assetid: f9b7c8b1-7a04-4eab-aa63-63efddb740fa
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# IPropertyPageImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert **IUnknown** und stellt eine Standardimplementierung der [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246)\-Schnittstelle.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
      template< class   
      T  
      >  
class IPropertyPageImpl  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `IPropertyPageImpl`.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[IPropertyPageImpl::IPropertyPageImpl](../Topic/IPropertyPageImpl::IPropertyPageImpl.md)|Konstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[IPropertyPageImpl::Activate](../Topic/IPropertyPageImpl::Activate.md)|Stellt das Dialogfeldfenster für die Eigenschaftenseite erstellt.|  
|[IPropertyPageImpl::Apply](../Topic/IPropertyPageImpl::Apply.md)|Wendet aktuelle Eigenschaftenseitenwerte zu den zugrunde liegenden Objekten, die von `SetObjects` angegeben werden.  Die ATL\-Implementierung gibt `S_OK` zurück.|  
|[IPropertyPageImpl::Deactivate](../Topic/IPropertyPageImpl::Deactivate.md)|Zerstört das Fenster, das mit **Activate** erstellt wird.|  
|[IPropertyPageImpl::GetPageInfo](../Topic/IPropertyPageImpl::GetPageInfo.md)|Ruft Informationen über die Eigenschaftenseite ab.|  
|[IPropertyPageImpl::Help](../Topic/IPropertyPageImpl::Help.md)|Aufrufs\-Windows\-Hilfe für die Eigenschaftenseite.|  
|[IPropertyPageImpl::IsPageDirty](../Topic/IPropertyPageImpl::IsPageDirty.md)|Gibt an, ob die Eigenschaftenseite geändert hat, nachdem sie aktiviert wurde.|  
|[IPropertyPageImpl::Move](../Topic/IPropertyPageImpl::Move.md)|Positionen und ändert das Buildeinstellungen Größe.|  
|[IPropertyPageImpl::SetDirty](../Topic/IPropertyPageImpl::SetDirty.md)|Kennzeichnet den Zustand der Eigenschaftenseite, wie geändert oder unverändert.|  
|[IPropertyPageImpl::SetObjects](../Topic/IPropertyPageImpl::SetObjects.md)|Stellt ein Array **IUnknown** Zeiger für die Objekte bereit, die mit der Eigenschaftenseite zugeordnet werden.  Diese Objekte empfangen die aktuellen Eigenschaftenseitenwerte durch einen Aufruf **Apply**.|  
|[IPropertyPageImpl::SetPageSite](../Topic/IPropertyPageImpl::SetPageSite.md)|Stellt die Eigenschaftenseite mit einem `IPropertyPageSite` Zeiger, durch den die Eigenschaftenseite den Eigenschaftenrahmen ist.|  
|[IPropertyPageImpl::Show](../Topic/IPropertyPageImpl::Show.md)|Stellt das Buildeinstellungen sichtbar oder nicht sichtbar erstellt.|  
|[IPropertyPageImpl::TranslateAccelerator](../Topic/IPropertyPageImpl::TranslateAccelerator.md)|Verarbeitet eine angegebene Tastatureingabe.|  
  
### Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[IPropertyPageImpl::m\_bDirty](../Topic/IPropertyPageImpl::m_bDirty.md)|Gibt an, ob der Zustand der Eigenschaftenseite geändert hat.|  
|[IPropertyPageImpl::m\_dwDocString](../Topic/IPropertyPageImpl::m_dwDocString.md)|Speichert den Ressourcenbezeichner, der der Textzeichenfolge zugeordnet wird, die die Eigenschaftenseite beschreibt.|  
|[IPropertyPageImpl::m\_dwHelpContext](../Topic/IPropertyPageImpl::m_dwHelpContext.md)|Speichert den Kontextbezeichner für das Hilfethema, das der Eigenschaftenseite zugeordnet ist.|  
|[IPropertyPageImpl::m\_dwHelpFile](../Topic/IPropertyPageImpl::m_dwHelpFile.md)|Speichert den Ressourcenbezeichner, der mit dem Namen der Hilfedatei zugeordnet wird, die die Eigenschaftenseite beschreibt.|  
|[IPropertyPageImpl::m\_dwTitle](../Topic/IPropertyPageImpl::m_dwTitle.md)|Speichert den Ressourcenbezeichner, der der Textzeichenfolge zugeordnet ist, die auf der Registerkarte für die Eigenschaftenseite angezeigt wird.|  
|[IPropertyPageImpl::m\_nObjects](../Topic/IPropertyPageImpl::m_nObjects.md)|Speichert die Anzahl von Objekten, die mit der Eigenschaftenseite zugeordnet werden.|  
|[IPropertyPageImpl::m\_pPageSite](../Topic/IPropertyPageImpl::m_pPageSite.md)|Punkte zur `IPropertyPageSite`\-Schnittstelle, durch die die Eigenschaftenseite den Eigenschaftenrahmen ist.|  
|[IPropertyPageImpl::m\_ppUnk](../Topic/IPropertyPageImpl::m_ppUnk.md)|Punkte in einem Array **IUnknown** Zeigern auf Objekte zugeordnete die.|  
|[IPropertyPageImpl::m\_size](../Topic/IPropertyPageImpl::m_size.md)|Speichert die Höhe und die Breite des Dialogfelds der Eigenschaftenseite, in Pixel.|  
  
## Hinweise  
 Die [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246)\-Schnittstelle können Objekte, um eine bestimmte Eigenschaftenseite innerhalb eines Eigenschaftenblatts zu verwalten.  Klasse `IPropertyPageImpl` stellt eine Standardimplementierung dieser Schnittstelle und implementiert **IUnknown**, indem Informationen zum Sicherungsgerät in Debugbuilds sendet.  
  
 **Verwandte Elemente** [ATL\-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL\-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## Vererbungshierarchie  
 `IPropertyPage`  
  
 `IPropertyPageImpl`  
  
## Anforderungen  
 **Header:** atlctl.h  
  
## Siehe auch  
 [IPropertyPage2Impl Class](../../atl/reference/ipropertypage2impl-class.md)   
 [IPerPropertyBrowsingImpl Class](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [ISpecifyPropertyPagesImpl Class](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)
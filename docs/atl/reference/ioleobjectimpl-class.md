---
title: "IOleObjectImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.IOleObjectImpl"
  - "ATL.IOleObjectImpl<T>"
  - "ATL::IOleObjectImpl"
  - "ATL::IOleObjectImpl<T>"
  - "IOleObjectImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Steuerelemente [C++], communication between container and control"
  - "IOleObject, ATL-Implementierung"
  - "IOleObjectImpl class"
ms.assetid: 59750b2d-1633-4a51-a4c2-6455b6b90c45
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IOleObjectImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert **IUnknown** und ist die Prinzipale Schnittstelle, über die ein Container ein Steuerelement ist.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
      template<  
class T   
>  
class ATL_NO_VTABLE IOleObjectImpl :  
public IOleObject  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `IOleObjectImpl`.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[IOleObjectImpl::Advise](../Topic/IOleObjectImpl::Advise.md)|Richtet eine Advise\-Verbindung mit dem Steuerelement ein.|  
|[IOleObjectImpl::Close](../Topic/IOleObjectImpl::Close.md)|Ändert den Steuerelementzustand für das Ausführen nach geladen.|  
|[IOleObjectImpl::DoVerb](../Topic/IOleObjectImpl::DoVerb.md)|Teilt das Steuerelement mit, um eine seiner aufgelisteten Aktionen auszuführen.|  
|[IOleObjectImpl::DoVerbDiscardUndo](../Topic/IOleObjectImpl::DoVerbDiscardUndo.md)|Teilt das Steuerelement mit, dass beliebige Rückgängigzustand zu verwerfen, den es beibehält.|  
|[IOleObjectImpl::DoVerbHide](../Topic/IOleObjectImpl::DoVerbHide.md)|Teilt das Steuerelement mit, um die Benutzeroberfläche von der Ansicht zu entfernen.|  
|[IOleObjectImpl::DoVerbInPlaceActivate](../Topic/IOleObjectImpl::DoVerbInPlaceActivate.md)|Führt das Steuerelement aus und installiert das Fenster installiert, aber nicht die Benutzeroberfläche des Steuerelements.|  
|[IOleObjectImpl::DoVerbOpen](../Topic/IOleObjectImpl::DoVerbOpen.md)|Veranlasst das Steuerelement, in einem separaten Fenster OPEN\-bearbeitetzu werden.|  
|[IOleObjectImpl::DoVerbPrimary](../Topic/IOleObjectImpl::DoVerbPrimary.md)|Führt die angegebene Aktion aus, wenn der Benutzer auf das Steuerelement doppelklickt.  Das Steuerelement definiert die Aktion, das direkte Steuerelement normalerweise zu aktivieren.|  
|[IOleObjectImpl::DoVerbShow](../Topic/IOleObjectImpl::DoVerbShow.md)|Zeigt dem Benutzer ein neu eingefügtes Steuerelement an.|  
|[IOleObjectImpl::DoVerbUIActivate](../Topic/IOleObjectImpl::DoVerbUIActivate.md)|Ermöglicht das direkte Steuerelement und zeigt die Benutzeroberfläche des Steuerelements, wie Menüs und Symbolleisten an.|  
|[IOleObjectImpl::EnumAdvise](../Topic/IOleObjectImpl::EnumAdvise.md)|Listet die Advise\-Verbindungen des Steuerelements auf.|  
|[IOleObjectImpl::EnumVerbs](../Topic/IOleObjectImpl::EnumVerbs.md)|Listet Aktionen für das Steuerelement aufgelistet.|  
|[IOleObjectImpl::GetClientSite](../Topic/IOleObjectImpl::GetClientSite.md)|Ruft die Clientsite des Steuerelements ab.|  
|[IOleObjectImpl::GetClipboardData](../Topic/IOleObjectImpl::GetClipboardData.md)|Ruft Daten aus der Zwischenablage ab.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
|[IOleObjectImpl::GetExtent](../Topic/IOleObjectImpl::GetExtent.md)|Ruft den Extent des Anzeigebereichs des Steuerelements ab.|  
|[IOleObjectImpl::GetMiscStatus](../Topic/IOleObjectImpl::GetMiscStatus.md)|Ruft den Status des Steuerelements ab.|  
|[IOleObjectImpl::GetMoniker](../Topic/IOleObjectImpl::GetMoniker.md)|Ruft den Moniker des Steuerelements ab.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
|[IOleObjectImpl::GetUserClassID](../Topic/IOleObjectImpl::GetUserClassID.md)|Ruft die Klassen\-ID des Steuerelements ab.|  
|[IOleObjectImpl::GetUserType](../Topic/IOleObjectImpl::GetUserType.md)|Ruft den Benutzertypnamen des Steuerelements ab.|  
|[IOleObjectImpl::InitFromData](../Topic/IOleObjectImpl::InitFromData.md)|Initialisiert das Steuerelement von ausgewählten Daten.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
|[IOleObjectImpl::IsUpToDate](../Topic/IOleObjectImpl::IsUpToDate.md)|Überprüft, ob das Steuerelement auf dem neuesten Stand ist.  Die ATL\-Implementierung gibt `S_OK` zurück.|  
|[IOleObjectImpl::OnPostVerbDiscardUndo](../Topic/IOleObjectImpl::OnPostVerbDiscardUndo.md)|Aufgerufen durch [DoVerbDiscardUndo](../Topic/IOleObjectImpl::DoVerbDiscardUndo.md) nach dem Rückgängigzustand wird verworfen.|  
|[IOleObjectImpl::OnPostVerbHide](../Topic/IOleObjectImpl::OnPostVerbHide.md)|Aufgerufen durch [DoVerbHide](../Topic/IOleObjectImpl::DoVerbHide.md) nach dem Steuerelement werden ausgeblendet.|  
|[IOleObjectImpl::OnPostVerbInPlaceActivate](../Topic/IOleObjectImpl::OnPostVerbInPlaceActivate.md)|Aufgerufen durch [DoVerbInPlaceActivate](../Topic/IOleObjectImpl::DoVerbInPlaceActivate.md) nach dem Steuerelement ist an der Stelle aktiviert.|  
|[IOleObjectImpl::OnPostVerbOpen](../Topic/IOleObjectImpl::OnPostVerbOpen.md)|Aufgerufen durch [DoVerbOpen](../Topic/IOleObjectImpl::DoVerbOpen.md), nachdem das Steuerelement zur Bearbeitung in einem separaten Fenster geöffnet wurde.|  
|[IOleObjectImpl::OnPostVerbShow](../Topic/IOleObjectImpl::OnPostVerbShow.md)|Aufgerufen durch [DoVerbShow](../Topic/IOleObjectImpl::DoVerbShow.md), nachdem das Steuerelement angezeigt hergestellt wurde.|  
|[IOleObjectImpl::OnPostVerbUIActivate](../Topic/IOleObjectImpl::OnPostVerbUIActivate.md)|Aufgerufen durch [DoVerbUIActivate](../Topic/IOleObjectImpl::DoVerbUIActivate.md), nachdem die Benutzeroberfläche des Steuerelements aktiviert wurde.|  
|[IOleObjectImpl::OnPreVerbDiscardUndo](../Topic/IOleObjectImpl::OnPreVerbDiscardUndo.md)|Aufgerufen durch [DoVerbDiscardUndo](../Topic/IOleObjectImpl::DoVerbDiscardUndo.md) vor dem Rückgängigzustand wird verworfen.|  
|[IOleObjectImpl::OnPreVerbHide](../Topic/IOleObjectImpl::OnPreVerbHide.md)|Aufgerufen durch [DoVerbHide](../Topic/IOleObjectImpl::DoVerbHide.md) vor dem Steuerelement werden ausgeblendet.|  
|[IOleObjectImpl::OnPreVerbInPlaceActivate](../Topic/IOleObjectImpl::OnPreVerbInPlaceActivate.md)|Aufgerufen durch [DoVerbInPlaceActivate](../Topic/IOleObjectImpl::DoVerbInPlaceActivate.md) vor dem Steuerelement ist an der Stelle aktiviert.|  
|[IOleObjectImpl::OnPreVerbOpen](../Topic/IOleObjectImpl::OnPreVerbOpen.md)|Aufgerufen durch [DoVerbOpen](../Topic/IOleObjectImpl::DoVerbOpen.md), bevor das Steuerelement zur Bearbeitung in einem separaten Fenster geöffnet wurde.|  
|[IOleObjectImpl::OnPreVerbShow](../Topic/IOleObjectImpl::OnPreVerbShow.md)|Aufgerufen durch [DoVerbShow](../Topic/IOleObjectImpl::DoVerbShow.md), bevor das Steuerelement angezeigt hergestellt wurde.|  
|[IOleObjectImpl::OnPreVerbUIActivate](../Topic/IOleObjectImpl::OnPreVerbUIActivate.md)|Aufgerufen durch [DoVerbUIActivate](../Topic/IOleObjectImpl::DoVerbUIActivate.md), bevor die Benutzeroberfläche des Steuerelements aktiviert wurde.|  
|[IOleObjectImpl::SetClientSite](../Topic/IOleObjectImpl::SetClientSite.md)|Verweist auf das Steuerelement über die Clientsite im Container.|  
|[IOleObjectImpl::SetColorScheme](../Topic/IOleObjectImpl::SetColorScheme.md)|Empfiehlt ein Farbschema der Anwendung des Steuerelements, sofern vorhanden.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
|[IOleObjectImpl::SetExtent](../Topic/IOleObjectImpl::SetExtent.md)|Legt den Umfang des Anzeigebereichs des Steuerelements fest.|  
|[IOleObjectImpl::SetHostNames](../Topic/IOleObjectImpl::SetHostNames.md)|Teilt dem Steuerelement die Namen der Containeranwendung und des Containerdokuments mit.|  
|[IOleObjectImpl::SetMoniker](../Topic/IOleObjectImpl::SetMoniker.md)|Teilt dem Steuerelement mit, wie der Moniker ist.  Die ATL\-Implementierung gibt **E\_NOTIMPL** zurück.|  
|[IOleObjectImpl::Unadvise](../Topic/IOleObjectImpl::Unadvise.md)|Löscht eine Advise\-Verbindung mit dem Steuerelement.|  
|[IOleObjectImpl::Update](../Topic/IOleObjectImpl::Update.md)|Aktualisiert das Steuerelement.  Die ATL\-Implementierung gibt `S_OK` zurück.|  
  
## Hinweise  
 Die [IOleObject](http://msdn.microsoft.com/library/windows/desktop/dd542709)\-Schnittstelle ist die grundlegende Schnittstelle, über die ein Container ein Steuerelement ist.  \- Klasse `IOleObjectImpl` stellt eine Standardimplementierung dieser Schnittstelle und implementiert **IUnknown**, indem Informationen zum Sicherungsgerät in Debugbuilds sendet.  
  
 **Verwandte Elemente** [ATL\-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL\-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## Vererbungshierarchie  
 `IOleObject`  
  
 `IOleObjectImpl`  
  
## Anforderungen  
 **Header:**  atlctl.h  
  
## Siehe auch  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [ActiveX Controls Interfaces](http://msdn.microsoft.com/library/windows/desktop/ms692724)   
 [Class Overview](../../atl/atl-class-overview.md)
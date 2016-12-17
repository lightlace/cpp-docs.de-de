---
title: "CComCompositeControl Class"
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
  - "CComCompositeControl"
  - "ATL::CComCompositeControl"
  - "ATL.CComCompositeControl<T>"
  - "ATL.CComCompositeControl"
  - "ATL::CComCompositeControl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComCompositeControl class"
  - "Zusammengesetzte Steuerelemente, CComCompositeControl class"
ms.assetid: 1304b931-27e8-4fbc-be8e-bb226ad887fb
caps.latest.revision: 21
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CComCompositeControl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt die Methoden, die erforderlich sind, um ein zusammengesetztes Steuerelement zu implementieren.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template <  
class T   
>  
class CComCompositeControl :  
public CComControl< T, CAxDialogImpl< T > >  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder von [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) sowie beliebiger anderer Schnittstellen möchten Sie für das zusammengesetzte Steuerelement unterstützen.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComCompositeControl::CComCompositeControl](../Topic/CComCompositeControl::CComCompositeControl.md)|Der \-Konstruktor.|  
|[CComCompositeControl::~CComCompositeControl](../Topic/CComCompositeControl::~CComCompositeControl.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComCompositeControl::AdviseSinkMap](../Topic/CComCompositeControl::AdviseSinkMap.md)|Rufen Sie diese Methode auf, um alle Steuerelemente Anmeldung oder abzumelden, die durch das zusammengesetzte Steuerelement gehostet werden.|  
|[CComCompositeControl::CalcExtent](../Topic/CComCompositeControl::CalcExtent.md)|Rufen Sie diese Methode auf, um die Größe in **HIMETRIC** Einheiten der Dialogfeldressource zu berechnen, die verwendet wird, um das zusammengesetzte Steuerelement zu hosten.|  
|[CComCompositeControl::Create](../Topic/CComCompositeControl::Create.md)|Diese Methode wird aufgerufen, um das Steuerelementfenster für das zusammengesetzte Steuerelement zu erstellen.|  
|[CComCompositeControl::CreateControlWindow](../Topic/CComCompositeControl::CreateControlWindow.md)|Rufen Sie diese Methode auf, um das Steuerelementfenster erstellen und jedes gehostete Steuerelement anzumelden.|  
|[CComCompositeControl::SetBackgroundColorFromAmbient](../Topic/CComCompositeControl::SetBackgroundColorFromAmbient.md)|Rufen Sie diese Methode auf, um die Hintergrundfarbe des zusammengesetzten Steuerelements mithilfe der Hintergrundfarbe des Containers festzulegen.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CComCompositeControl::m\_hbrBackground](../Topic/CComCompositeControl::m_hbrBackground.md)|Der Hintergrundpinsel.|  
|[CComCompositeControl::m\_hWndFocus](../Topic/CComCompositeControl::m_hWndFocus.md)|Das Handle des Fensters, das gerade den Fokus besitzt.|  
  
## Hinweise  
 Die Klassen, die von der Klasse `CComCompositeControl` abgeleitet werden, erben die Funktionalität eines ActiveX\-zusammengesetztenSteuerelements.  ActiveX\-Steuerelemente, die von `CComCompositeControl` abgeleitet werden, wird durch ein Standarddialogfeld gehostet.  Diese Typen von Steuerelementen werden zusammengesetzte Steuerelemente aufgerufen, da sie in der Lage sind, andere Steuerelemente zu hosten \(systemeigene Windows\-Steuerelement\- und ActiveX\-Steuerelemente\).  
  
 `CComCompositeControl` identifiziert die Dialogfeldressource, um zu verwenden, wenn das zusammengesetzte Steuerelement erstellt, indem es einen aufgelisteten Datenmember in der untergeordneten Klasse sucht.  Der Member IDD dieser untergeordneten Klasse wird dem Ressourcen\-ID der Dialogfeldressource festgelegt, die als das Fenster des Steuerelements verwendet wird.  Das folgende Beispiel des Datenmembers, den die Klasse, die von `CComCompositeControl` abgeleitet wird, enthalten soll, um die für das Fenster verwendet werden Dialogfeldressource zu identifizieren, des Steuerelements:  
  
 [!CODE [NVC_ATL_COM#13](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#13)]  
  
> [!NOTE]
>  Zusammengesetzte Steuerelemente sind immer Steuerelemente mit Fenster, obwohl sie fensterlose Steuerelemente enthalten können.  
  
 Ein Steuerelement implementiert wird `CComCompositeControl` von abgeleitete Klasse hat das standardmäßige integrierte Drücken der TAB\-TASTEen\-Verhalten.  Wenn das Steuerelement den Fokus erhält, von in mit der TAB\-TASTE werden einer enthaltenen Anwendung, die TAB\-TASTE drücken nacheinander bewirkt wurde den Fokus, durch die Steuerelemente alle zusammengesetzten Steuerelements, dann aus dem zusammengesetzten Steuerelement ausgelesen und an zum nächsten Element in der Aktivierreihenfolge des Containers durchlaufen werden.  Die Aktivierreihenfolge der gehosteten Steuerelemente wird durch die Dialogfeldressource bestimmt und die Reihenfolge, in der Drücken der TAB\-TASTE auftritt.  
  
> [!NOTE]
>  Damit Zugriffstasten ordnungsgemäß arbeiten mit `CComCompositeControl`, ist es notwendig, eine Zugriffstastentabelle zu laden, wie das Steuerelement erstellt wird, werden das Handle und die Anzahl von Zugriffstasten zurück in [IOleControlImpl::GetControlInfo](../Topic/IOleControlImpl::GetControlInfo.md) und zerstört schließlich die Tabelle, wenn das Steuerelement freigegeben wird.  
  
## Beispiel  
 [!CODE [NVC_ATL_COM#14](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#14)]  
  
## Vererbungshierarchie  
 `WinBase`  
  
 [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)  
  
 [CComControl](../../atl/reference/ccomcontrol-class.md)  
  
 `CComCompositeControl`  
  
## Anforderungen  
 **Header:**  atlctl.h  
  
## Siehe auch  
 [CComControl Class](../../atl/reference/ccomcontrol-class.md)   
 [Grundlagen von zusammengesetzten Steuerelementen](../../atl/atl-composite-control-fundamentals.md)   
 [Class Overview](../../atl/atl-class-overview.md)
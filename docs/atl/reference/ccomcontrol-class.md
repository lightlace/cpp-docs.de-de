---
title: "CComControl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComControl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ambient properties"
  - "CComControl class"
  - "CComControlBase class, CComControl class"
  - "control flags"
  - "Steuerelemente [ATL], control helper functions"
  - "Steuerelemente [ATL], Eigenschaften"
  - "Basiseigenschaften, ATL"
ms.assetid: 55368c27-bd16-45a7-b701-edb36157c8e8
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CComControl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Erstellen und Verwalten von ATL\-Steuerelementen bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template <  
class T,  
class WinBase= CWindowImpl< T>   
>  
class ATL_NO_VTABLE CComControl :  
public CComControlBase, public WinBase;  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die das Steuerelement implementiert.  
  
 *WinBase*  
 Die Basisklasse, die Fensterfunktionen implementiert.  Standardwerte zu [CWindowImpl](../../atl/reference/cwindowimpl-class.md).  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComControl::CComControl](../Topic/CComControl::CComControl.md)|Konstruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComControl::ControlQueryInterface](../Topic/CComControl::ControlQueryInterface.md)|Ruft einen Zeiger auf die angeforderte Schnittstelle ab.|  
|[CComControl::CreateControlWindow](../Topic/CComControl::CreateControlWindow.md)|Stellt ein Fenster für das Steuerelement.|  
|[CComControl::FireOnChanged](../Topic/CComControl::FireOnChanged.md)|Benachrichtigt die Senke des Containers, dass eine Steuerelementeigenschaft geändert hat.|  
|[CComControl::FireOnRequestEdit](../Topic/CComControl::FireOnRequestEdit.md)|Benachrichtigt die Senke des Containers, dass eine Steuerelementeigenschaft im Begriff ist zu ändern und das Objekt ist, die Senke fragend, wie fortgesetzt wird.|  
|[CComControl::MessageBox](../Topic/CComControl::MessageBox.md)|Rufen Sie diese Methode auf, um ein Meldungsfeld, anzuzeigen und zu bearbeiten.|  
  
## Hinweise  
 `CComControl` ist ein Satz von nützliche Steuerhilfsfunktionen und wesentliche Datenmember für ATL\-Steuerelementen.  Wenn Sie ein Standardsteuerelement oder ein DHTML\-Steuerelement mit dem ATL\-Steuerelement\-Assistenten erstellen, berechnet der Assistent automatisch die Klasse von `CComControl`.  `CComControl` berechnet die meisten der Methoden von [CComControlBase](../../atl/reference/ccomcontrolbase-class.md).  
  
 Weitere Informationen zum Erstellen eines Steuerelements, finden Sie unter [ATL\-Lernprogramm](../../atl/active-template-library-atl-tutorial.md).  Weitere Informationen zu den ATL\-Projekt\-Assistenten, finden Sie im Artikel [Erstellen eines ATL\-Projekts](../../atl/reference/creating-an-atl-project.md).  
  
 Eine Beispiel von `CComControl`\-Methoden und \-Datenmember, finden Sie im [CIRC](../../top/visual-cpp-samples.md) Beispiel.  
  
## Vererbungshierarchie  
 `WinBase`  
  
 [CComControlBase](../../atl/reference/ccomcontrolbase-class.md)  
  
 `CComControl`  
  
## Anforderungen  
 **Header:**  atlctl.h  
  
## Siehe auch  
 [CWindowImpl Class](../../atl/reference/cwindowimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComControlBase Class](../../atl/reference/ccomcontrolbase-class.md)   
 [CComCompositeControl Class](../../atl/reference/ccomcompositecontrol-class.md)
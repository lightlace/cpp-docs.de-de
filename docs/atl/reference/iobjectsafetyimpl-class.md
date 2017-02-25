---
title: "IObjectSafetyImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IObjectSafetyImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Steuerelemente [ATL], safe"
  - "IObjectSafety, ATL-Implementierung"
  - "IObjectSafetyImpl class"
  - "safe for scripting and initialization (controls)"
ms.assetid: 64e32082-d910-4a8a-a5bf-ebed9145359d
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IObjectSafetyImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt eine Standardimplementierung der `IObjectSafety`\-Schnittstelle, um einen Client ermöglichen, Sicherheitsebenen eines Objekts abzurufen und festzulegen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] ausführen.  
  
## Syntax  
  
```  
  
      template <class   
      T  
      , DWORD   
      dwSupportedSafety  
      >  
class IObjectSafetyImpl  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `IObjectSafetyImpl`.  
  
 *dwSupportedSafety*  
 Gibt die unterstützten Sicherheitsoptionen für das Steuerelement.  Kann einer der folgenden Werte sein:  
  
-   **INTERFACESAFE\_FOR\_UNTRUSTED\_CALLER** die Schnittstelle, die von den [SetInterfaceSafetyOptions](../Topic/IObjectSafetyImpl::SetInterfaceSafetyOptions.md)\-Parameter `riid` identifiziert wird, sollte sicher gemacht werden für die Skripterstellung.  
  
-   **INTERFACESAFE\_FOR\_UNTRUSTED\_DATA** die Schnittstelle, die von den `SetInterfaceSafetyOptions`\-Parameter `riid` identifiziert wird, sollte sicher gemacht werden für nicht vertrauenswürdige Daten während der Initialisierung.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[IObjectSafetyImpl::GetInterfaceSafetyOptions](../Topic/IObjectSafetyImpl::GetInterfaceSafetyOptions.md)|Ruft die Sicherheitsoptionen ab, die vom Objekt unterstützt werden, sowie die Sicherheitsoptionen, die derzeit für das Objekt festgelegt werden.|  
|[IObjectSafetyImpl::SetInterfaceSafetyOptions](../Topic/IObjectSafetyImpl::SetInterfaceSafetyOptions.md)|Stellt das Objektsafe für Initialisierung oder Skripterstellung erstellt.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[IObjectSafetyImpl::m\_dwCurrentSafety](../Topic/IObjectSafetyImpl::m_dwCurrentSafety.md)|Speichert die aktuelle Sicherheitsebene des Objekts.|  
  
## Hinweise  
 \- Klasse `IObjectSafetyImpl` stellt eine Standardimplementierung von `IObjectSafety`.  Die `IObjectSafety`\-Schnittstelle ermöglicht einem Client, um Sicherheitsebenen eines Objekts abzurufen und festzulegen.  Beispielsweise kann ein Webbrowser **IObjectSafety::SetInterfaceSafetyOptions** aufrufen, um ein Steuersafe für Initialisierung oder safe für die Skripterstellung zu erstellen.  
  
 Beachten Sie das mithilfe des [IMPLEMENTED\_CATEGORY](../Topic/IMPLEMENTED_CATEGORY.md)\-Makros mit **CATID\_SafeForScripting** und **CATID\_SafeForInitializing** Teilkategorien bietet eine alternative Möglichkeit, dass eine Komponente sicher ist.  
  
 **Verwandte Elemente** [ATL\-Lernprogramm](../../atl/active-template-library-atl-tutorial.md), [Erstellen eines ATL\-Projekts](../../atl/reference/creating-an-atl-project.md)  
  
## Vererbungshierarchie  
 `IObjectSafety`  
  
 `IObjectSafetyImpl`  
  
## Anforderungen  
 **Header:**  atlctl.h  
  
## Siehe auch  
 [IObjectSafety Interface](https://msdn.microsoft.com/en-us/library/aa768224.aspx)   
 [Class Overview](../../atl/atl-class-overview.md)
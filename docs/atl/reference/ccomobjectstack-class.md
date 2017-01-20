---
title: "CComObjectStack Class"
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
  - "ATL::CComObjectStack"
  - "ATL.CComObjectStack"
  - "ATL::CComObjectStack<Base>"
  - "ATL.CComObjectStack<Base>"
  - "CComObjectStack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComObjectStack class"
ms.assetid: 3da72c40-c834-45f6-bb76-6ac204028d80
caps.latest.revision: 19
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CComObjectStack Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse erstellt ein temporäres COM\-Objekt und gibt den mit einer skelettartigen Implementierung von **IUnknown**.  
  
## Syntax  
  
```  
  
      template<  
   class Base   
>  
class CComObjectStack :  
   public Base  
```  
  
#### Parameter  
 `Base`  
 Die Klasse, die von abgeleitet [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) oder von [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) sowie von jeder anderen Schnittstelle möchten Sie auf das Objekt unterstützen.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComObjectStack::CComObjectStack](../Topic/CComObjectStack::CComObjectStack.md)|Der \-Konstruktor.|  
|[CComObjectStack::~CComObjectStack](../Topic/CComObjectStack::~CComObjectStack.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComObjectStack::AddRef](../Topic/CComObjectStack::AddRef.md)|Gibt null.  Im Debugmodus Aufrufe `_ASSERTE`.|  
|[CComObjectStack::QueryInterface](../Topic/CComObjectStack::QueryInterface.md)|Gibt **E\_NOINTERFACE**.  Im Debugmodus Aufrufe `_ASSERTE`.|  
|[CComObjectStack::Release](../Topic/CComObjectStack::Release.md)|Gibt null.  Im Debugmodus Aufrufe `_ASSERTE`.  ~|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CComObjectStack::m\_hResFinalConstruct](../Topic/CComObjectStack::m_hResFinalConstruct.md)|Enthält  **HRESULT**, das während der Konstruktion des `CComObjectStack`\-Objekts zurückgegeben wird.|  
  
## Hinweise  
 `CComObjectStack` wird verwendet, um ein temporäres COM\-Objekt erstellen und das Objekt bereitzustellen skelettartige eine Implementierung von **IUnknown**.  In der Regel wird das Objekt wie eine lokale Variable in einer Funktion verwendet \(also, gedrückt auf dem Stapel\).  Da das Objekt zerstört wird, wenn die Funktion, Verweiszählung nicht ausgeführt wird, um die Effizienz zu erhöhen.  
  
 Im folgenden Beispiel wird gezeigt, wie ein COM\-Objekt erstellt, das innerhalb einer Funktion verwendet wird:  
  
 [!CODE [NVC_ATL_COM#42](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#42)]  
  
 Das temporäre Objekt `Tempobj` wird auf dem Stapel abgelegt und wird automatisch wenn die Funktionsende.  
  
## Vererbungshierarchie  
 `Base`  
  
 `CComObjectStack`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [CComAggObject Class](../../atl/reference/ccomaggobject-class.md)   
 [CComObject Class](../../atl/reference/ccomobject-class.md)   
 [CComObjectGlobal Class](../../atl/reference/ccomobjectglobal-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)
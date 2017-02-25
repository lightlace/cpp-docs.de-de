---
title: "CComEnumImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComEnumImpl"
  - "ATL::CComEnumImpl"
  - "CComEnumImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComEnumImpl class"
ms.assetid: cc0d8e76-e608-46db-87cd-4c7161fe32d2
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComEnumImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt die Implementierung für eine COM\-Enumeratorschnittstelle bereit, in der die Elemente, die aufgelistet werden, in einem Array gespeichert werden.  
  
## Syntax  
  
```  
  
      template <  
   class Base,  
   const IID* piid,  
   class T,  
   class Copy  
>  
class ATL_NO_VTABLE CComEnumImpl :   
   public Base  
```  
  
#### Parameter  
 `Base`  
 Eine COM\-Enumerator \([IEnumXXXX](https://msdn.microsoft.com/en-us/library/ms680089.aspx)\)\-Schnittstelle.  
  
 `piid`  
 Ein Zeiger auf den Schnittstellen\-ID der Enumeratorschnittstelle.  
  
 `T`  
 Der Typ des Elements verfügbar gemacht die Enumeratorschnittstelle.  
  
 `Copy`  
 Homogenes [Kopierrichtlinienklasse](../../atl/atl-copy-policy-classes.md).  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComEnumImpl::CComEnumImpl](../Topic/CComEnumImpl::CComEnumImpl.md)|Der \-Konstruktor.|  
|[CComEnumImpl::~CComEnumImpl](../Topic/CComEnumImpl::~CComEnumImpl.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComEnumImpl::Clone](../Topic/CComEnumImpl::Clone.md)|Die Implementierung von [IEnumXXXX::Clone](https://msdn.microsoft.com/en-us/library/ms690336.aspx).|  
|[CComEnumImpl::Init](../Topic/CComEnumImpl::Init.md)|Initialisiert den Enumerator.|  
|[CComEnumImpl::Next](../Topic/CComEnumImpl::Next.md)|Die Implementierung von [IEnumXXXX::Next](https://msdn.microsoft.com/en-us/library/ms695273.aspx).|  
|[CComEnumImpl::Reset](../Topic/CComEnumImpl::Reset.md)|Die Implementierung von [IEnumXXXX::Reset](https://msdn.microsoft.com/en-us/library/ms693414.aspx).|  
|[CComEnumImpl::Skip](../Topic/CComEnumImpl::Skip.md)|Die Implementierung von [IEnumXXXX::Skip](https://msdn.microsoft.com/en-us/library/ms690392.aspx).|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CComEnumImpl::m\_begin](../Topic/CComEnumImpl::m_begin.md)|Ein Zeiger auf das erste Element im Array.|  
|[CComEnumImpl::m\_dwFlags](../Topic/CComEnumImpl::m_dwFlags.md)|Kopienflags weitergegeben `Init`.|  
|[CComEnumImpl::m\_end](../Topic/CComEnumImpl::m_end.md)|Ein Zeiger auf den Speicherort direkt über dem letzten Element im Array hinaus.|  
|[CComEnumImpl::m\_iter](../Topic/CComEnumImpl::m_iter.md)|Ein Zeiger auf das aktuelle Element im Array.|  
|[CComEnumImpl::m\_spUnk](../Topic/CComEnumImpl::m_spUnk.md)|Der **IUnknown** Zeiger des Objekts die Auflistung angibt, die aufgelistet wird.|  
  
## Hinweise  
 `CComEnumImpl` stellt die Implementierung für eine COM\-Enumeratorschnittstelle bereit, in der die Elemente, die aufgelistet werden, in einem Array gespeichert werden.  Diese Klasse ist der `IEnumOnSTLImpl`\-Klasse analog, die eine Implementierung einer Enumeratorschnittstelle auf Grundlage eines STL\-Container bereitstellt.  
  
> [!NOTE]
>  Ausführliche Informationen über weitere Unterschiede zwischen `CComEnumImpl` und `IEnumOnSTLImpl`, finden Sie unter [CComEnumImpl::Init](../Topic/CComEnumImpl::Init.md).  
  
 In der Regel müssen Sie *nicht*, um eine eigene Enumeratorklasse erstellen, indem Sie aus dieser Schnittstellenimplementierung berechnen.  Wenn Sie einen ATL\-angegebenen Enumerator auf einem Array verwenden möchten, ist es häufig, eine Instanz von [CComEnum](../../atl/reference/ccomenum-class.md) zu erstellen.  
  
 Wenn Sie jedoch einen benutzerdefinierten Enumerator bereitstellen müssen \(beispielsweise, einer, Schnittstellen zusätzlich zur Enumeratorschnittstelle verfügbar gemacht\), können Sie diese Klasse ableiten.  In dieser Situation ist es wahrscheinlich, dass Sie die [CComEnumImpl::Clone](../Topic/CComEnumImpl::Clone.md)\-Methode überschreiben müssen, um eine eigene Implementierung bereitzustellen.  
  
 Weitere Informationen finden Sie unter [ATL\-Auflistungen und \-Enumeratoren](../../atl/atl-collections-and-enumerators.md).  
  
## Vererbungshierarchie  
 `Base`  
  
 `CComEnumImpl`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [IEnumOnSTLImpl Class](../../atl/reference/ienumonstlimpl-class.md)   
 [CComEnum Class](../../atl/reference/ccomenum-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)
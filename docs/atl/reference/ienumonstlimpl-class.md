---
title: "IEnumOnSTLImpl Class"
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
  - "IEnumOnSTLImpl"
  - "ATL.IEnumOnSTLImpl"
  - "ATL::IEnumOnSTLImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IEnumOnSTLImpl class"
ms.assetid: 1789e77b-88b8-447d-a490-806b918912ce
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# IEnumOnSTLImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse definiert eine Enumeratorschnittstelle auf Grundlage einer STL\-Auflistung.  
  
## Syntax  
  
```  
  
      template <  
   class Base,  
   const IID* piid,  
   class T,  
   class Copy,  
   class CollType  
>  
class ATL_NO_VTABLE IEnumOnSTLImpl :  
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
 [Kopierrichtlinienklasse](../../atl/atl-copy-policy-classes.md).  
  
 `CollType`  
 Eine STL\-Containerklasse.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[IEnumOnSTLImpl::Clone](../Topic/IEnumOnSTLImpl::Clone.md)|Die Implementierung von [IEnumXXXX::Clone](https://msdn.microsoft.com/en-us/library/ms690336.aspx).|  
|[IEnumOnSTLImpl::Init](../Topic/IEnumOnSTLImpl::Init.md)|Initialisiert den Enumerator.|  
|[IEnumOnSTLImpl::Next](../Topic/IEnumOnSTLImpl::Next.md)|Die Implementierung von [IEnumXXXX::Next](https://msdn.microsoft.com/en-us/library/ms695273.aspx).|  
|[IEnumOnSTLImpl::Reset](../Topic/IEnumOnSTLImpl::Reset.md)|Die Implementierung von [IEnumXXXX::Reset](https://msdn.microsoft.com/en-us/library/ms693414.aspx).|  
|[IEnumOnSTLImpl::Skip](../Topic/IEnumOnSTLImpl::Skip.md)|Die Implementierung von [IEnumXXXX::Skip](https://msdn.microsoft.com/en-us/library/ms690392.aspx).|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[IEnumOnSTLImpl::m\_iter](../Topic/IEnumOnSTLImpl::m_iter.md)|Der Iterator, der der aktuellen Position des Enumerators innerhalb der Auflistung darstellt.|  
|[IEnumOnSTLImpl::m\_pcollection](../Topic/IEnumOnSTLImpl::m_pcollection.md)|Ein Zeiger auf STL\-Container, der die aufgelistet werden Elemente enthalten.|  
|[IEnumOnSTLImpl::m\_spUnk](../Topic/IEnumOnSTLImpl::m_spUnk.md)|Der **IUnknown** Zeiger des Objekts die Auflistung angibt.|  
  
## Hinweise  
 `IEnumOnSTLImpl` stellt die Implementierung für eine COM\-Enumeratorschnittstelle bereit, in der die Elemente, die aufgelistet werden, in einem STL\-kompatiblen Container gespeichert werden.  Diese Klasse ist der [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)\-Klasse analog, die eine Implementierung für eine Enumeratorschnittstelle auf einem Array bereitstellt.  
  
> [!NOTE]
>  Siehe [CComEnumImpl::Init](../Topic/CComEnumImpl::Init.md) für Informationen über weitere Unterschiede zwischen `CComEnumImpl` und `IEnumOnSTLImpl`.  
  
 In der Regel müssen Sie *nicht*, um eine eigene Enumeratorklasse erstellen, indem Sie aus dieser Schnittstellenimplementierung berechnen.  Wenn Sie einen ATL\-angegebenen Enumerator auf Grundlage eines STL\-Container verwenden möchten, ist es häufig, eine Instanz von [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md) zu erstellen, oder eine Auflistungsklasse erstellen, die einen Enumerator zurückgibt, indem von [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md) abgeleitet.  
  
 Wenn Sie jedoch einen benutzerdefinierten Enumerator bereitstellen müssen \(beispielsweise, einer, Schnittstellen zusätzlich zur Enumeratorschnittstelle verfügbar gemacht\), können Sie diese Klasse ableiten.  In dieser Situation ist es wahrscheinlich, dass Sie die [Klon](../Topic/IEnumOnSTLImpl::Clone.md)\-Methode überschreiben müssen, um eine eigene Implementierung bereitzustellen.  
  
## Vererbungshierarchie  
 `Base`  
  
 `IEnumOnSTLImpl`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)
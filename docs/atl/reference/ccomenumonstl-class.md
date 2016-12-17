---
title: "CComEnumOnSTL Class"
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
  - "CComEnumOnSTL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComEnumOnSTL class"
ms.assetid: befe1a44-7a00-4f28-9a2e-cc0fa526643c
caps.latest.revision: 21
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CComEnumOnSTL Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse definiert ein COM\-Enumeratorobjekt auf Grundlage einer STL\-Auflistung.  
  
## Syntax  
  
```  
  
      template <  
   class Base,  
   const IID* piid,  
   class T,  
   class Copy,  
   class CollType,  
   class ThreadModel = CComObjectThreadModel  
>  
class ATL_NO_VTABLE CComEnumOnSTL :  
   public IEnumOnSTLImpl<Base, piid, T, Copy, CollType>,  
   public CComObjectRootEx< ThreadModel >  
```  
  
#### Parameter  
 `Base`  
 Eine COM\-Enumerator \([IEnumXXXX](https://msdn.microsoft.com/en-us/library/ms680089.aspx)\)\-Schnittstelle.  
  
 `piid`  
 Ein Zeiger auf den Schnittstellen\-ID der Enumeratorschnittstelle.  
  
 `T`  
 Der Typ des Elements verfügbar gemacht die Enumeratorschnittstelle.  
  
 `Copy`  
 Eine [Kopierrichtlinienklassen](../../atl/atl-copy-policy-classes.md)\-Klasse.  
  
 `CollType`  
 Eine STL\-Containerklasse.  
  
## Hinweise  
 `CComEnumOnSTL` definiert ein COM\-Enumeratorobjekt auf Grundlage einer STL\-Auflistung.  Diese Klasse kann allein oder in Verbindung mit [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md) verwendet werden.  Typische Schritte für die Verwendung dieser Klasse werden unten erläutert.  Weitere Informationen finden Sie unter [ATL\-Auflistungen und \-Enumeratoren](../../atl/atl-collections-and-enumerators.md).  
  
## Um diese Klasse mit ICollectionOnSTLImpl verwenden:  
  
-   `typedef` eine Spezialisierung dieser Klasse.  
  
-   Verwenden Sie `typedef` als das endgültige Vorlagenargument in einer Spezialisierung von `ICollectionOnSTLImpl`.  
  
 Siehe [ATL\-Auflistungen und \-Enumeratoren](../../atl/atl-collections-and-enumerators.md) als ein Beispiel.  
  
## Um diese Klasse unabhängig ICollectionOnSTLImpl verwenden:  
  
-   `typedef` eine Spezialisierung dieser Klasse.  
  
-   Verwenden Sie `typedef` als Vorlagenargument in einer Spezialisierung von `CComObject`.  
  
-   Erstellen Sie eine Instanz der `CComObject` Spezialisierung.  
  
-   Initialisieren Sie das Enumeratorobjekt, indem Sie [IEnumOnSTLImpl::Init](../Topic/IEnumOnSTLImpl::Init.md) aufrufen.  
  
-   Geben Sie die Enumeratorschnittstelle an den Client zurück.  
  
## Vererbungshierarchie  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)  
  
 `CComEnumOnSTL`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Beispiel  
 Der Code, der unten angezeigt wird, stellt eine generische Funktion, um die Erstellung und die Initialisierung eines Enumeratorobjekts bearbeiten:  
  
 [!CODE [NVC_ATL_COM#34](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#34)]  
  
 Diese Vorlagenfunktion kann verwendet werden, um die `_NewEnum`\-Eigenschaft einer Auflistungsschnittstelle wie unten gezeigt zu implementieren:  
  
 [!CODE [NVC_ATL_COM#35](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#35)]  
  
 Dieser Code erstellt `typedef` für `CComEnumOnSTL`, der einen Vektor von `CComVariant` s mithilfe der **IEnumVariant**\-Schnittstelle verfügbar macht.  Die Klasse **CVariantCollection** spezialisiert einfach **CreateSTLEnumerator**, um mit Enumeratorobjekten dieses Typs zu arbeiten.  
  
## Siehe auch  
 [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)   
 [ATLCollections\-Beispiel: Veranschaulicht ICollectionOnSTLImpl, CComEnumOnSTL und benutzerdefinierte Kopierrichtlinienklassen](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [CComObjectThreadModel](../Topic/CComObjectThreadModel.md)   
 [IEnumOnSTLImpl Class](../../atl/reference/ienumonstlimpl-class.md)
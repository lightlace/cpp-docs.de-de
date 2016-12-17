---
title: "CComEnum Class"
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
  - "CComEnum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComEnum class"
ms.assetid: bff7dd7b-eb6e-4d6e-96ed-2706e66c8b3b
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CComEnum Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse definiert ein COM\-Enumeratorobjekt auf einem Array.  
  
## Syntax  
  
```  
  
      template <  
   class Base,  
   const IID* piid,  
   class T,  
   class Copy,  
   class ThreadModel = CcomObjectThreadModel  
>  
class ATL_NO_VTABLE CComEnum :  
   public CComEnumImpl<Base, piid, T, Copy>,  
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
 Homogenes [Kopierrichtlinienklasse](../../atl/atl-copy-policy-classes.md).  
  
 `ThreadModel`  
 Das Threadingmodell der Klasse.  Dieser Parameter wird standardmäßig der globalen Objektthreadmodell, das im Projekt verwendet wird.  
  
## Hinweise  
 `CComEnum` definiert ein COM\-Enumeratorobjekt auf einem Array.  Diese Klasse ist [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md) analog, die einen Enumerator auf Grundlage eines STL\-Container implementiert.  Typische Schritte für die Verwendung dieser Klasse werden unten erläutert.  Weitere Informationen finden Sie unter [ATL\-Auflistungen und \-Enumeratoren](../../atl/atl-collections-and-enumerators.md).  
  
## Um diese Klasse verwenden:  
  
-   `typedef` eine Spezialisierung dieser Klasse.  
  
-   Verwenden Sie `typedef` als Vorlagenargument in einer Spezialisierung von `CComObject`.  
  
-   Erstellen Sie eine Instanz der `CComObject` Spezialisierung.  
  
-   Initialisieren Sie das Enumeratorobjekt, indem Sie [CComEnumImpl::Init](../Topic/CComEnumImpl::Init.md) aufrufen.  
  
-   Geben Sie die Enumeratorschnittstelle an den Client zurück.  
  
## Vererbungshierarchie  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)  
  
 `CComEnum`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Beispiel  
 Der Code, der unten angezeigt wird, stellt eine wiederverwendbare Funktion zum Erstellen und Initialisieren eines Enumeratorobjekts bereit.  
  
 [!CODE [NVC_ATL_COM#32](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#32)]  
  
 Diese Vorlagenfunktion kann verwendet werden, um die `_NewEnum`\-Eigenschaft einer Auflistungsschnittstelle wie unten gezeigt zu implementieren:  
  
 [!CODE [NVC_ATL_COM#33](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#33)]  
  
 Dieser Code erstellt `typedef` für `CComEnum`, der einen Vektor von **VARIANT** s durch die **IEnumVariant**\-Schnittstelle verfügbar macht.  Die Klasse **CVariantArrayCollection** spezialisiert einfach **CreateEnumerator**, um mit Enumeratorobjekten dieses Typs zu arbeiten und führt die notwendigen Argumente an.  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComObjectThreadModel](../Topic/CComObjectThreadModel.md)   
 [CComEnumImpl Class](../../atl/reference/ccomenumimpl-class.md)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)
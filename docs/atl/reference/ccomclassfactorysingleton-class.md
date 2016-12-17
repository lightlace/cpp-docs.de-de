---
title: "CComClassFactorySingleton Class"
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
  - "ATL.CComClassFactorySingleton"
  - "ATL.CComClassFactorySingleton<T>"
  - "ATL::CComClassFactorySingleton"
  - "ATL::CComClassFactorySingleton<T>"
  - "CComClassFactorySingleton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComClassFactorySingleton class"
ms.assetid: debb983c-382b-487b-8d42-7ea26dc158b8
caps.latest.revision: 21
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CComClassFactorySingleton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse wird von [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) und [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) verwendet, um ein einzelnes Objekt zu erstellen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template<  
class T  
>  
class CComClassFactorySingleton :  
public CComClassFactory  
```  
  
#### Parameter  
 `T`  
 Ihre Klasse.  
  
 `CComClassFactorySingleton` wird von abgeleitet [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) und [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) verwendet, um ein einzelnes Objekt zu erstellen.  Jeder Aufruf der Methode `CreateInstance` fragt einfach dieses Objekt für einen Schnittstellenzeiger ab.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComClassFactorySingleton::CreateInstance](../Topic/CComClassFactorySingleton::CreateInstance.md)|Fragt `m_spObj` für einen Schnittstellenzeiger ab.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CComClassFactorySingleton::m\_spObj](../Topic/CComClassFactorySingleton::m_spObj.md)|Das [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)\-Objekt erstellt durch `CComClassFactorySingleton`.|  
  
## Hinweise  
 ATL\-Objekte rufen normalerweise eine Klassenfactory ab, indem von [CComCoClass](../../atl/reference/ccomcoclass-class.md) berechnen.  Diese Klasse enthält das Makro [DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md), das `CComClassFactory` als Standardklassenfactory deklariert.  Um `CComClassFactorySingleton` zu verwenden, geben Sie die [DECLARE\_CLASSFACTORY\_SINGLETON](../Topic/DECLARE_CLASSFACTORY_SINGLETON.md)\-Makro in der Klassendefinition des Objekts an.  Beispiel:  
  
 [!CODE [NVC_ATL_COM#10](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#10)]  
  
## Vererbungshierarchie  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)  
  
 `CComClassFactorySingleton`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [CComClassFactory2 Class](../../atl/reference/ccomclassfactory2-class.md)   
 [CComClassFactoryAutoThread Class](../../atl/reference/ccomclassfactoryautothread-class.md)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md)   
 [Class Overview](../../atl/atl-class-overview.md)
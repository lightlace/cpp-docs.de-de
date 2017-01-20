---
title: "CComClassFactory Class"
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
  - "ATL.CComClassFactory"
  - "CComClassFactory"
  - "ATL::CComClassFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComClassFactory class"
ms.assetid: e56dacf7-d5c4-4c42-aef4-a86d91981a1b
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CComClassFactory Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert die Schnittstelle [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364).  
  
## Syntax  
  
```  
  
   class CComClassFactory : public IClassFactory,   
public CComObjectRootEx< CComGlobalsThreadModel >  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComClassFactory::CreateInstance](../Topic/CComClassFactory::CreateInstance.md)|Erstellt ein Objekt des angegebenen CLSID.|  
|[CComClassFactory::LockServer](../Topic/CComClassFactory::LockServer.md)|Sperrt die Klassenfactory im Arbeitsspeicher.|  
  
## Hinweise  
 `CComClassFactory` [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) implementiert die Schnittstelle, die Methoden zum Erstellen eines Objekts eines bestimmten CLSID enthält, sowie die Klassenfactory im Arbeitsspeicher, um schneller erstellt werden sperrt Objekte zu ermöglichen die neuen.  **IClassFactory** muss für jede Klasse implementiert werden, in der Sie in der Systemregistrierung registrieren und, zu dem Sie einem CLSID zuweisen.  
  
 ATL\-Objekte rufen normalerweise eine Klassenfactory ab, indem von [CComCoClass](../../atl/reference/ccomcoclass-class.md) berechnen.  Diese Klasse enthält das Makro [DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md), das `CComClassFactory` als Standardklassenfactory deklariert.  Um diesen Standard zu überschreiben, geben Sie eines der Makros `DECLARE_CLASSFACTORY`*XXX* in der Klassendefinition.  Zum Beispiel verwendet das [DECLARE\_CLASSFACTORY\_EX](../Topic/DECLARE_CLASSFACTORY_EX.md)\-Makro die angegebene Klasse für die Klassenfactory:  
  
 [!CODE [NVC_ATL_COM#8](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#8)]  
  
 Die oben aufgeführte Klassendefinition gibt an, dass **CMyClassFactory** als die Standardklassenfactory des Objekts verwendet wird.  **CMyClassFactory** muss von `CComClassFactory` ableiten und `CreateInstance` überschreiben.  
  
 ATL stellt drei weitere Makros, die eine Klassenfactory deklarieren:  
  
-   [DECLARE\_CLASSFACTORY2](../Topic/DECLARE_CLASSFACTORY2.md) verwendet [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), das Erstellen von eine Lizenz steuert.  
  
-   [DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md) verwendet [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md), das Objekte in mehreren Apartments erstellt.  
  
-   [DECLARE\_CLASSFACTORY\_SINGLETON](../Topic/DECLARE_CLASSFACTORY_SINGLETON.md) verwendet [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md), das ein einzelnes [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)\-Objekt erstellt.  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md)   
 [Class Overview](../../atl/atl-class-overview.md)
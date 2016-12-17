---
title: "CComClassFactoryAutoThread Class"
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
  - "ATL::CComClassFactoryAutoThread"
  - "ATL.CComClassFactoryAutoThread"
  - "CComClassFactoryAutoThread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComClassFactoryAutoThread class"
ms.assetid: 22008042-533f-4dd9-bf7e-191ee571f9a1
caps.latest.revision: 21
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CComClassFactoryAutoThread Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert die Schnittstelle [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) und die in mehreren Apartments erstellt werden Objekte.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      class CComClassFactoryAutoThread : public IClassFactory,   
public CComObjectRootEx< CComGlobalsThreadModel >  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComClassFactoryAutoThread::CreateInstance](../Topic/CComClassFactoryAutoThread::CreateInstance.md)|Erstellt ein Objekt des angegebenen CLSID.|  
|[CComClassFactoryAutoThread::LockServer](../Topic/CComClassFactoryAutoThread::LockServer.md)|Sperrt die Klassenfactory im Arbeitsspeicher.|  
  
## Hinweise  
 `CComClassFactoryAutoThread` ist zu [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) ähnlich, jedoch können die in mehreren Apartments erstellt werden Objekte.  Um diese Unterstützung zu nutzen, leiten Sie das EXE\-Modul von [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
 ATL\-Objekte rufen normalerweise eine Klassenfactory ab, indem von [CComCoClass](../../atl/reference/ccomcoclass-class.md) berechnen.  Diese Klasse enthält das Makro [DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md), das [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) als Standardklassenfactory deklariert.  Um `CComClassFactoryAutoThread` zu verwenden, geben Sie die [DECLARE\_CLASSFACTORY\_AUTO\_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md)\-Makro in der Klassendefinition des Objekts an.  Beispiel:  
  
 [!CODE [NVC_ATL_COM#9](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#9)]  
  
## Vererbungshierarchie  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 `CComClassFactoryAutoThread`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [CComClassFactory2 Class](../../atl/reference/ccomclassfactory2-class.md)   
 [CComClassFactorySingleton Class](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md)   
 [Class Overview](../../atl/atl-class-overview.md)
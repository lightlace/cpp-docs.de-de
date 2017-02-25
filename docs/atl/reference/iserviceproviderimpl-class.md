---
title: "IServiceProviderImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::IServiceProviderImpl<T>"
  - "ATL.IServiceProviderImpl<T>"
  - "ATL.IServiceProviderImpl"
  - "ATL::IServiceProviderImpl"
  - "IServiceProviderImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IServiceProvider-Schnittstelle, ATL-Implementierung"
  - "IServiceProviderImpl class"
ms.assetid: 251254d3-c4ce-40d7-aee0-3d676d1d72f2
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# IServiceProviderImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt eine Standardimplementierung der Schnittstelle `IServiceProvider`.  
  
## Syntax  
  
```  
  
      template <  
   class T  
>   
class ATL_NO_VTABLE IServiceProviderImpl :  
   public IServiceProvider  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `IServiceProviderImpl`.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[IServiceProviderImpl::QueryService](../Topic/IServiceProviderImpl::QueryService.md)|Erstellt oder greift auf den angegebenen Dienst zu und gibt einen Schnittstellenzeiger auf die angegebene Schnittstelle für den Dienst zurück.|  
  
## Hinweise  
 Die `IServiceProvider`\-Schnittstelle lokalisiert einen Dienst, der von der GUID angegeben und gibt den Schnittstellenzeiger für die angeforderte Schnittstelle auf dem Dienst zurück.  \- Klasse `IServiceProviderImpl` stellt eine Standardimplementierung dieser Schnittstelle.  
  
 **IServiceProviderImpl**  gibt eine Methode an: [QueryService](../Topic/IServiceProviderImpl::QueryService.md), das einen Schnittstellenzeiger auf die angegebene Schnittstelle für den Dienst erstellt oder Zugriff auf den angegebenen Dienst und zurückgibt.  
  
 `IServiceProviderImpl` verwendet eine Dienstzuordnung, beginnend mit [BEGIN\_SERVICE\_MAP](../Topic/BEGIN_SERVICE_MAP.md) und auf [END\_SERVICE\_MAP](../Topic/END_SERVICE_MAP.md).  
  
 Die Dienstzuordnung enthält zwei Einträge: [SERVICE\_ENTRY](../Topic/SERVICE_ENTRY.md), das eine angegebene Dienst\-ID \(SID\) unterstützt durch das Objekt angibt, und [SERVICE\_ENTRY\_CHAIN](../Topic/SERVICE_ENTRY_CHAIN.md), das `QueryService` aufruft, um zu einem anderen Objekt zu verketten.  
  
## Vererbungshierarchie  
 `IServiceProvider`  
  
 `IServiceProviderImpl`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)
---
title: "CComGITPtr Class"
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
  - "ATL::CComGITPtr<T>"
  - "CComGITPtr"
  - "ATL.CComGITPtr"
  - "ATL.CComGITPtr<T>"
  - "ATL::CComGITPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComGITPtr class"
ms.assetid: af895acb-525a-4555-bb67-b241b7df515b
caps.latest.revision: 19
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CComGITPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zur Handhabung von Schnittstellenzeigern und die globale Schnittstellentabelle bereit \(GIT\).  
  
## Syntax  
  
```  
  
      template <  
   class T   
>  
class CComGITPtr  
```  
  
#### Parameter  
 `T`  
 Der Typ des im GIT Schnittstellenzeigers, gespeichert werden.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComGITPtr::CComGITPtr](../Topic/CComGITPtr::CComGITPtr.md)|Der \-Konstruktor.|  
|[CComGITPtr::~CComGITPtr](../Topic/CComGITPtr::~CComGITPtr.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComGITPtr::Attach](../Topic/CComGITPtr::Attach.md)|Rufen Sie diese Methode auf, um den Schnittstellenzeiger in der globalen Schnittstellentabelle \(GIT\) zu registrieren.|  
|[CComGITPtr::CopyTo](../Topic/CComGITPtr::CopyTo.md)|Rufen Sie diese Methode auf, um die Schnittstelle aus der globalen Schnittstellentabelle \(GIT\) mit dem übergebenen Zeiger zu kopieren.|  
|[CComGITPtr::Detach](../Topic/CComGITPtr::Detach.md)|Rufen Sie diese Methode auf, um die Schnittstelle aus dem `CComGITPtr`\-Objekt aufzuheben.|  
|[CComGITPtr::GetCookie](../Topic/CComGITPtr::GetCookie.md)|Rufen Sie diese Methode auf, um das Cookie aus dem `CComGITPtr`\-Objekt zurückzugeben.|  
|[CComGITPtr::Revoke](../Topic/CComGITPtr::Revoke.md)|Rufen Sie diese Methode auf, um die Schnittstelle aus der globalen Schnittstellentabelle \(GIT\) zu entfernen.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComGITPtr::operator DWORD](../Topic/CComGITPtr::operator%20DWORD.md)|Gibt das Cookie aus dem `CComGITPtr`\-Objekt zurück.|  
|[CComGITPtr::operator \=](../Topic/CComGITPtr::operator%20=.md)|Zuweisungsoperator|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CComGITPtr::m\_dwCookie](../Topic/CComGITPtr::m_dwCookie.md)|Das Cookie.|  
  
## Hinweise  
 Objekte, die den Free\-Threaded Marshaller und die Anforderung aggregieren, Schnittstellenzeiger zu verwenden, aus anderen Objekten müssen zusätzliche Schritte unternehmen, um sicherzustellen, dass die Schnittstellen ordnungsgemäß gemarshallt werden.  In der Regel bedeutet dies, die Schnittstellenzeiger zu speichern in das GIT mit ein und den Zeiger vom GIT abzurufen, wenn es verwendet wird.  Die Klasse `CComGITPtr` wird bereitgestellt, um Ihnen helfen, die Schnittstellenzeiger zu verwenden, die im GIT gespeichert werden.  
  
> [!NOTE]
>  Die globale Schnittstellentabellenfunktion ist unter Windows 95 mit DCOM\-Version 1.1 und höher, Windows 98, Windows NT 4.0 mit Service Pack 3 und höher und Windows 2000 nur verfügbar.  
  
## Anforderungen  
 **Header:** atlbase.h  
  
## Siehe auch  
 [Freethreaded Marshaller](../../atl/atl-and-the-free-threaded-marshaler.md)   
 [Accessing Interfaces Across Apartments](http://msdn.microsoft.com/library/windows/desktop/ms682353)   
 [When to Use the Global Interface Table](http://msdn.microsoft.com/library/windows/desktop/ms693729)   
 [Class Overview](../../atl/atl-class-overview.md)
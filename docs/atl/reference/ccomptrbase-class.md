---
title: "CComPtrBase Class"
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
  - "ATL.CComPtrBase"
  - "ATL::CComPtrBase<T>"
  - "ATL.CComPtrBase<T>"
  - "ATL::CComPtrBase"
  - "CComPtrBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComPtrBase class"
ms.assetid: 6dbe9543-dee8-4a97-b02f-dd3a25f4a1a0
caps.latest.revision: 19
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CComPtrBase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse bietet eine Grundlage für Klassen des intelligenten Zeigermechanismus mithilfe der Routinen COM\-basierten des Arbeitsspeichers.  
  
## Syntax  
  
```  
  
      template <  
   class T   
> class CComPtrBase  
```  
  
#### Parameter  
 `T`  
 Der vom intelligenten Zeiger verwiesen werden, Objekttyp.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComPtrBase::~CComPtrBase](../Topic/CComPtrBase::~CComPtrBase.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComPtrBase::Advise](../Topic/CComPtrBase::Advise.md)|Rufen Sie diese Methode auf, um eine Verbindung zwischen dem Verbindungspunkt von `CComPtrBase` und der Senke eines Clients zu erstellen.|  
|[CComPtrBase::Attach](../Topic/CComPtrBase::Attach.md)|Rufen Sie diese Methode auf, um den Besitz einer vorhandenen Zeiger zu akzeptieren.|  
|[CComPtrBase::CoCreateInstance](../Topic/CComPtrBase::CoCreateInstance.md)|Rufen Sie diese Methode, um ein Objekt der Klasse auf, die mit angegebenen Klassen\-ID oder ID zu programmieren zugeordnet ist|  
|[CComPtrBase::CopyTo](../Topic/CComPtrBase::CopyTo.md)|Rufen Sie diese Methode auf, um den `CComPtrBase` Zeiger auf eine andere Zeigervariable zu kopieren.|  
|[CComPtrBase::Detach](../Topic/CComPtrBase::Detach.md)|Rufen Sie diese Methode auf, um den Besitz eines Zeigers freizugeben.|  
|[CComPtrBase::IsEqualObject](../Topic/CComPtrBase::IsEqualObject.md)|Rufen Sie diese Methode auf, um zu überprüfen, ob die angegebenen **IUnknown** Punkte auf denselben zugeordnetes mit dem `CComPtrBase`\-Objekt Objekts.|  
|[CComPtrBase::QueryInterface](../Topic/CComPtrBase::QueryInterface.md)|Rufen Sie diese Methode auf, um einen Zeiger auf eine angegebene Schnittstelle zurückzugeben.|  
|[CComPtrBase::Release](../Topic/CComPtrBase::Release.md)|Rufen Sie diese Methode auf, um die Schnittstelle freizugeben.|  
|[CComPtrBase::SetSite](../Topic/CComPtrBase::SetSite.md)|Rufen Sie diese Methode auf, um die Website `CComPtrBase` des Objekts zu **IUnknown** des übergeordneten Objekts festzulegen.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComPtrBase::operator T\*](../Topic/CComPtrBase::operator%20T*.md)|Der Umwandlungsoperator.|  
|[CComPtrBase::operator \!](../Topic/CComPtrBase::operator%20!.md)|Der NOT\-Operator.|  
|[CComPtrBase::operator &](../Topic/CComPtrBase::operator%20&.md)|Der &\-Operator.|  
|[CComPtrBase::operator \*](../Topic/CComPtrBase::operator%20*.md)|Der Operator " \* ".|  
|[CComPtrBase::operator \<](../Topic/CComPtrBase::operator%20%3C.md)|Der Kleiner\-als\-Operator.|  
|[CComPtrBase::operator \=\=](../Topic/CComPtrBase::operator%20==.md)|Der Gleichheitsoperator.|  
|[CComPtrBase::operator \-\>](../Topic/CComPtrBase::operator%20-%3E.md)|Der Operator Zeiger\-auf\-Member.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CComPtrBase::p](../Topic/CComPtrBase::p.md)|Die Zeigerdatenmembervariable.|  
  
## Hinweise  
 Diese Klasse stellt die Grundlage für andere intelligenten Zeiger, die COM\-Speicherverwaltungsroutinen verwenden, wie [CComQIPtr](../../atl/reference/ccomqiptr-class.md) und [CComPtr](../../atl/reference/ccomptr-class.md).  Die abgeleiteten Klassen fügen eigene Konstruktoren und Operatoren hinzu, sondern überlassen auf die Methoden, die von `CComPtrBase` bereitgestellt werden.  
  
## Anforderungen  
 **Header:** atlcomcli.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)
---
title: "CAutoVectorPtr Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAutoVectorPtr"
  - "ATL.CAutoVectorPtr"
  - "ATL.CAutoVectorPtr<T>"
  - "CAutoVectorPtr"
  - "ATL::CAutoVectorPtr<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoVectorPtr class"
ms.assetid: 0030362b-6bc4-4a47-9b5b-3c3899dceab4
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CAutoVectorPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt ein Objekt des intelligenten Zeigermechanismus mithilfe des neuen Vektor\- und der delet\-Operatoren dar.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template<  
typename T  
> class CAutoVectorPtr  
```  
  
#### Parameter  
 `T`  
 Der Zeigertyp.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAutoVectorPtr::CAutoVectorPtr](../Topic/CAutoVectorPtr::CAutoVectorPtr.md)|Der \-Konstruktor.|  
|[CAutoVectorPtr::~CAutoVectorPtr](../Topic/CAutoVectorPtr::~CAutoVectorPtr.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAutoVectorPtr::Allocate](../Topic/CAutoVectorPtr::Allocate.md)|Rufen Sie diese Methode auf, um den Arbeitsspeicher zuzuordnen, der durch das Array benötigt wird, das auf durch `CAutoVectorPtr` gezeigt wird.|  
|[CAutoVectorPtr::Attach](../Topic/CAutoVectorPtr::Attach.md)|Rufen Sie diese Methode auf, um den Besitz einer vorhandenen Zeiger zu akzeptieren.|  
|[CAutoVectorPtr::Detach](../Topic/CAutoVectorPtr::Detach.md)|Rufen Sie diese Methode auf, um den Besitz eines Zeigers freizugeben.|  
|[CAutoVectorPtr::Free](../Topic/CAutoVectorPtr::Free.md)|Rufen Sie diese Methode auf, um ein Objekt zu löschen, das von zu `CAutoVectorPtr` gezeigt wird.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAutoVectorPtr::operator T \*](../Topic/CAutoVectorPtr::operator%20T%20*.md)|Der Umwandlungsoperator.|  
|[CAutoVectorPtr::operator \=](../Topic/CAutoVectorPtr::operator%20=.md)|Der Zuweisungsoperator.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CAutoVectorPtr::m\_p](../Topic/CAutoVectorPtr::m_p.md)|Die Zeigerdatenmembervariable.|  
  
## Hinweise  
 Diese Klasse stellt Methoden zum Erstellen und Verwalten eines intelligenten Zeigermechanismus bereit, der wird verhindert, dass Speicherverluste schützen, indem automatisch Ressourcen freigibt, wenn er außerhalb des gültigen Bereichs liegt.  `CAutoVectorPtr` ist zu `CAutoPtr`, der einzige Unterschied vergleichbar, der dieser `CAutoVectorPtr` Verwendung [Vektor neu &#91;&#93;](../Topic/operator%20new\(%3Cnew%3E\).md) und [Vektorlöschung &#91;&#93;](../Topic/operator%20delete\(%3Cnew%3E\).md), Arbeitsspeicher statt C\+\+ **new** und **delete**\-Operatoren reserviert und freigegeben ist.  Siehe [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md), wenn Auflistungsklassen von `CAutoVectorPtr` erforderlich sind.  
  
 Siehe [CAutoPtr](../../atl/reference/cautoptr-class.md) als ein Beispiel für die Verwendung einer Klasse des intelligenten Zeigermechanismus.  
  
## Anforderungen  
 **Header:** atlbase.h  
  
## Siehe auch  
 [CAutoPtr Class](../../atl/reference/cautoptr-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)
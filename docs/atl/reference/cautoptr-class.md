---
title: "CAutoPtr Class"
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
  - "CAutoPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAutoPtr class"
ms.assetid: 08988d53-4fb0-4711-bdfc-8ac29c63f410
caps.latest.revision: 23
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CAutoPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt ein Objekt des intelligenten Zeigermechanismus dar.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template<   
typename T  
>  
class CAutoPtr  
```  
  
#### Parameter  
 `T`  
 Der Zeigertyp.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAutoPtr::CAutoPtr](../Topic/CAutoPtr::CAutoPtr.md)|Der \-Konstruktor.|  
|[CAutoPtr::~CAutoPtr](../Topic/CAutoPtr::~CAutoPtr.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAutoPtr::Attach](../Topic/CAutoPtr::Attach.md)|Rufen Sie diese Methode auf, um den Besitz einer vorhandenen Zeiger zu akzeptieren.|  
|[CAutoPtr::Detach](../Topic/CAutoPtr::Detach.md)|Rufen Sie diese Methode auf, um den Besitz eines Zeigers freizugeben.|  
|[CAutoPtr::Free](../Topic/CAutoPtr::Free.md)|Rufen Sie diese Methode auf, um ein Objekt zu löschen, das von zu `CAutoPtr` gezeigt wird.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAutoPtr::operator T\*](../Topic/CAutoPtr::operator%20T*.md)|Der Umwandlungsoperator.|  
|[CAutoPtr::operator \=](../Topic/CAutoPtr::operator%20=.md)|Der Zuweisungsoperator.|  
|[CAutoPtr::operator \-\>](../Topic/CAutoPtr::operator%20-%3E.md)|Der Operator Zeiger\-auf\-Member.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CAutoPtr::m\_p](../Topic/CAutoPtr::m_p.md)|Die Zeigerdatenmembervariable.|  
  
## Hinweise  
 Diese Klasse stellt Methoden zum Erstellen und Verwalten eines intelligenten Zeigermechanismus bereit, der wird verhindert, dass Speicherverluste schützen, indem automatisch Ressourcen freigibt, wenn er außerhalb des gültigen Bereichs liegt.  
  
 Darüber hinaus übertragen der Kopierkonstruktor und Zuweisungsoperator von `CAutoPtr` den Besitz des Zeigers, kopieren den Quellzeiger zum Zielzeiger und legen den Quellzeiger auf NULL fest.  Es ist daher nicht möglich, zwei `CAutoPtr`\-Objekte jedes zu verfügen, die den gleichen Zeiger speichert, und dieses reduziert die Möglichkeit von den gleichen Zeiger zweimal löschen.  
  
 `CAutoPtr` vereinfacht auch die Erstellung von Auflistungen Zeiger.  Anstatt, eine Auflistungsklasse berechnen und den Destruktor zu überschreiben, ist es einfacher, eine Auflistung von Objekten `CAutoPtr` auszuführen.  Wenn die Auflistung gelöscht wird, `CAutoPtr` verlassen die Objekte im Bereich löschen und sich automatisch.  
  
 [CHeapPtr](../../atl/reference/cheapptr-class.md) und Varianten funktionieren auf die gleiche Weise wie `CAutoPtr`, außer dass sie belegen und geben Arbeitsspeicher mit verschiedenen Heapfunktionen statt C\+\+ **new** und **delete**\-Operatoren frei.  [CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md) ist zu `CAutoPtr`, der ähnlich, der einzige Unterschied ist, dass es **vector new\[\]** und **vector delete\[\]** verwendet, um Arbeitsspeicher reserviert und freigegeben.  
  
 Siehe auch [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) und [CAutoPtrList](../../atl/reference/cautoptrlist-class.md), wenn Arrays oder Listen von intelligenten Zeiger erforderlich sind.  
  
## Anforderungen  
 **Header:** atlbase.h  
  
## Beispiel  
 [!CODE [NVC_ATL_Utilities#74](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#74)]  
  
## Siehe auch  
 [CHeapPtr Class](../../atl/reference/cheapptr-class.md)   
 [CAutoVectorPtr Class](../../atl/reference/cautovectorptr-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)
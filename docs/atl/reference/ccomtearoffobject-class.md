---
title: "CComTearOffObject Class"
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
  - "ATL::CComTearOffObject<Base>"
  - "ATL::CComTearOffObject"
  - "ATL.CComTearOffObject"
  - "ATL.CComTearOffObject<Base>"
  - "CComTearOffObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComTearOffObject class"
  - "tear-off interfaces"
  - "tear-off interfaces, ATL"
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CComTearOffObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert eine Tearoff\-Schnittstelle.  
  
## Syntax  
  
```  
  
      template<  
   class Base   
>  
class CComTearOffObject :  
   public Base  
```  
  
#### Parameter  
 `Base`  
 Tearoffe die Klasse, abgeleitet von `CComTearOffObjectBase` und Schnittstellen möchten Sie das Tearoffes Objekt zur Unterstützung.  
  
 ATL implementiert ihre Tearoff\-Schnittstellen in zwei Phasen \- die `CComTearOffObjectBase`\-Methoden behandeln den Verweiszähler und `QueryInterface`, während `CComTearOffObject`[IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) implementiert.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComTearOffObject::CComTearOffObject](../Topic/CComTearOffObject::CComTearOffObject.md)|Der \-Konstruktor.|  
|[CComTearOffObject::~CComTearOffObject](../Topic/CComTearOffObject::~CComTearOffObject.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComTearOffObject::AddRef](../Topic/CComTearOffObject::AddRef.md)|Inkrementiert den Verweiszähler für ein `CComTearOffObject`\-Objekt.|  
|[CComTearOffObject::QueryInterface](../Topic/CComTearOffObject::QueryInterface.md)|Gibt einen Zeiger auf die angeforderte Schnittstelle auf jedem Tearoffe die Klasse oder die Besitzerklasse zurück.|  
|[CComTearOffObject::Release](../Topic/CComTearOffObject::Release.md)|Dekrementiert den Verweiszähler für ein `CComTearOffObject`\-Objekt zerstört und ihn.|  
  
### CComTearOffObjectBase\-Methoden  
  
|||  
|-|-|  
|[CComTearOffObjectBase](../Topic/CComTearOffObject::CComTearOffObjectBase.md)|Konstruktor.|  
  
### CComTearOffObjectBase\-Datenmember  
  
|||  
|-|-|  
|[m\_pOwner](../Topic/CComTearOffObject::m_pOwner.md)|Ein Zeiger auf `CComObject` berechnete aus der Besitzerklasse.|  
  
## Hinweise  
 `CComTearOffObject` implementiert eine Tearoff\-Schnittstelle als separates Objekt, das instanziiert wird, wenn diese Schnittstelle für abgefragt wird.  Das Tearoff wird gelöscht, wenn sein Zähler auf Null ist.  Normalerweise erstellen Sie eine Tearoff\-Schnittstelle für eine Schnittstelle, die selten verwendet wird, da ein, Tearoff verwenden, einen Zeiger in allen Instanzen des Hauptzwecks speichert.  
  
 Sie sollten die Klasse ableiten, die das Tearoff von `CComTearOffObjectBase` implementiert und von, welche Schnittstellen Sie das Tearoffes Objekt zur Unterstützung soll.  `CComTearOffObjectBase` ist auf der Besitzerklasse und dem Threadmodell vorlagenbasierten.  Die Besitzerklasse ist die Klasse des Objekts, für das ein Tearoff implementiert wird.  Wenn Sie kein Threadmodell angeben, wird das standardmäßige Threadmodell verwendet.  
  
 Sie sollten eine COM\-Zuordnung für die Tearoffe Klasse erstellen.  Wenn das ATL Tearoff instanziiert, erstellt er **CComTearOffObject\<CYourTearOffClass\>** oder **CComCachedTearOffObject\<CYourTearOffClass\>**.  
  
 Beispielsweise im \- Beispiel, ist die `CBeeper2`\-Klasse die Tearoffe Klasse und die `CBeeper`\-Klasse ist die Besitzerklasse:  
  
 [!CODE [NVC_ATL_COM#43](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#43)]  
  
## Vererbungshierarchie  
 `Base`  
  
 `CComTearOffObject`  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [CComCachedTearOffObject Class](../../atl/reference/ccomcachedtearoffobject-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)
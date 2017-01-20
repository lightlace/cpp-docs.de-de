---
title: "WeakReference-Klasse"
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
  - "implements/Microsoft::WRL::Details::WeakReference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WeakReference-Klasse"
ms.assetid: 3f4c956b-dbbd-49b1-8cfa-9509a9956c97
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# WeakReference-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
class WeakReference;  
```  
  
## Hinweise  
 Stellt einen *schwachen Verweis dar,*, der der Windows Runtime oder dem klassischen COM verwendet werden kann.  Ein schwacher Verweis stellt ein Objekt dar, das möglicherweise oder möglicherweise nicht möglich ist.  
  
 Ein `WeakReference`\-Objekt verwaltet einen *starken Verweis*, das ein Zeiger auf ein Objekt ist, und einen *starken Verweiszähler* bei, der die Anzahl der Kopien des starken Verweis aufweist, die von der Resolve\(\)\- Methode verteilt wurden.  Während der starke Verweiszähler nicht 0 ist, wird der starke Verweis gültig und das Objekt kann.  Wenn der Verweiszähler starke null, wird der starke Verweis ungültig und das Objekt ist jedoch nicht zugänglich.  
  
 Ein WeakReference\-Objekt wird normalerweise verwendet, um ein Objekt repräsentiert, dessen Vorhandensein von ein externer Thread oder Anwendung gesteuert wird.  Erstellen Sie beispielsweise WeakReference\-Objekt von einen Verweis auf ein Dateiobjekt.  Während die Datei geöffnet wird, wird der starke Verweis gültig.  jedoch, wenn die Datei geschlossen wird, wird der starke Verweis ungültig.  
  
 Die WeakReference\-Methoden sind threadsicher.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[WeakReference::WeakReference\-Konstruktor](../windows/weakreference-weakreference-constructor.md)|Initialisiert eine neue Instanz der WeakReference\-Klasse.|  
|[WeakReference::~WeakReference\-Destruktor](../windows/weakreference-tilde-weakreference-destructor.md)|Deinitialisert \(zerstört\) die aktuelle Instanz der WeakReference\-Klasse.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[WeakReference::DecrementStrongReference\-Methode](../windows/weakreference-decrementstrongreference-method.md)|Dekrementiert den starken Verweiszählerwert des aktuellen WeakReference\-Objekts.|  
|[WeakReference::IncrementStrongReference\-Methode](../windows/weakreference-incrementstrongreference-method.md)|Inkrementiert den starken Verweiszählerwert des aktuellen WeakReference\-Objekts.|  
|[WeakReference::Resolve\-Methode](../windows/weakreference-resolve-method.md)|Legt den angegebenen Zeiger auf den aktuellen starken Verweiswert fest, ob der starke Verweiszähler nicht 0 ist.|  
|[WeakReference::SetUnknown\-Methode](../windows/weakreference-setunknown-method.md)|Legt den starken Verweis des aktuellen WeakReference\-Objekts dem angegebenen Schnittstellenzeiger fest.|  
  
## Vererbungshierarchie  
 `WeakReference`  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)
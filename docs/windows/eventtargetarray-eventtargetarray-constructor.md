---
title: "EventTargetArray::EventTargetArray-Konstruktor"
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
  - "event/Microsoft::WRL::Details::EventTargetArray::EventTargetArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EventTargetArray, Konstruktor"
ms.assetid: 6c6d3737-3cd3-4515-a8f6-d27901bb8ed2
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# EventTargetArray::EventTargetArray-Konstruktor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
EventTargetArray(  
   _Out_ HRESULT* hr,  
   size_t items  
);  
```  
  
#### Parameter  
 `hr`  
 Nach Vorgängen dieses Konstruktors gibt Parameter `hr` an, ob Zuordnung des Arrays erfolgreich war oder fehlgeschlagen ist.  Die folgende Tabelle zeigt die möglichen Werte für `hr` auf.  
  
 S\_OK  
 Der Vorgang erfolgreich.  
  
 E\_OUTOFMEMORY  
 Arbeitsspeicher konnte nicht für das Array zugeordnet werden.  
  
 S\_FALSE  
 Parameter `items` ist kleiner oder gleich null.  
  
 `items`  
 Die Anzahl der zuzuordnenden den Arrayelementen.  
  
## Hinweise  
 Initialisiert eine neue Instanz der EventTargetArray\-Klasse.  
  
 EventTargetArray wird verwendet, um ein Array Ereignishandler in einem EventSource\-Objekt zu halten.  
  
## Anforderungen  
 **Header:** event.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [EventTargetArray\-Klasse](../windows/eventtargetarray-class.md)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)
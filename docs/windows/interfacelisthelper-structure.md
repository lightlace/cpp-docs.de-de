---
title: "InterfaceListHelper-Struktur"
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
  - "implements/Microsoft::WRL::Details::InterfaceListHelper"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InterfaceListHelper-Struktur"
ms.assetid: 4297e419-c96b-45df-8a00-7568062125ba
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# InterfaceListHelper-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
template <  
   typename T0,  
   typename T1 = Nil,  
   typename T2 = Nil,  
   typename T3 = Nil,  
   typename T4 = Nil,  
   typename T5 = Nil,  
   typename T6 = Nil,  
   typename T7 = Nil,  
   typename T8 = Nil,  
   typename T9 = Nil  
>  
struct InterfaceListHelper;  
  
template <  
   typename T0  
>  
struct InterfaceListHelper<T0, Nil, Nil, Nil, Nil, Nil, Nil, Nil, Nil>;  
```  
  
#### Parameter  
 `T0`  
 Vorlagenparameter 0, der erforderlich ist.  
  
 `T1`  
 Vorlagenparameter 1, standardmäßig nicht angegeben ist.  
  
 `T2`  
 Vorlagenparameter 2, standardmäßig nicht angegeben ist. Der dritte Vorlagenparameter.  
  
 `T3`  
 Vorlagenparameter 3, standardmäßig nicht angegeben ist.  
  
 `T4`  
 Vorlagenparameter 4, standardmäßig nicht angegeben ist.  
  
 `T5`  
 Vorlagenparameter 5, standardmäßig nicht angegeben ist.  
  
 `T6`  
 Vorlagenparameter 6, standardmäßig nicht angegeben ist.  
  
 `T7`  
 Vorlagenparameter 7, standardmäßig nicht angegeben ist.  
  
 `T8`  
 Vorlagenparameter 8, standardmäßig nicht angegeben ist.  
  
 `T9`  
 Vorlagenparameter 9, standardmäßig nicht angegeben ist.  
  
## Hinweise  
 Erstellt einen InterfaceList\-Typ, indem die angegebenen Vorlagenparameterargumente rekursiv anwenden.  
  
 Die InterfaceListHelper\-Vorlage Vorlagenparameter verwendet `T0`, um den ersten Datenmember in einer InterfaceList\-Struktur definieren und dann wird rekursiv die InterfaceListHelper\-Vorlage allen verbleibenden Vorlagenparametern.  InterfaceListHelper stoppt, wenn keine verbleibenden Vorlagenparameter gibt.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`TypeT`|Ein Synonym für den InterfaceList\-Typ.|  
  
## Vererbungshierarchie  
 `InterfaceListHelper`  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)
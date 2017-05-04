---
title: "Agile::operator=-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::operator="
ms.assetid: 2c413bef-f103-4911-afb3-0dac5f6a760e
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::operator=-Operator
Weist das angegebene Objekt dem aktuellen Agile\-Objekt zu.  
  
## Syntax  
  
```cpp  
  
   Agile<T> operator=(  
   T^ object  
) throw();  
  
   Agile<T> operator=(  
      const Agile<T>& object  
) throw();  
  
   Agile<T> operator=(  
      Agile<T>&& object  
) throw();  
  
   T^ operator=(  
      IUnknown* lp  
) throw();  
  
```  
  
#### Parameter  
 `T`  
 Der durch den Vorlagentypnamen spezifizierte Typ.  
  
 `object`  
 Das Objekt oder das Handle für ein Objekt, das auf das aktuelle Agile\-Objekt kopiert oder verschoben wird.  
  
 `lp`  
 Der IUnknown\-Schnittstellenzeiger eines Objekts.  
  
## Rückgabewert  
 Ein Handle für ein Objekt des Typs `T`  
  
## Hinweise  
 Die erste Version des Zuweisungsoperators kopiert ein Handle für einen Verweistyp zum aktuellen Agile\-Objekt. Die zweite Version kopiert einen Verweis zu einem Agile\-Typ zum aktuellen Agile\-Objekt. Die dritte Version verschiebt einen Agile\-Typ zum aktuellen Agile\-Objekt. Die vierte Version verschiebt einen Zeiger auf ein COM\-Objekt zum aktuellen Agile\-Objekt.  
  
 Der Zuweisungsvorgang speichert automatisch den Kontext des aktuellen Agile\-Objekts.  
  
## Anforderungen  
 **Unterstützter Client \(Mindestversion\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Mindestversion\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Header:** vccorlib.h  
  
## Siehe auch  
 [Platform::Agile\-Klasse](../cppcx/platform-agile-class.md)
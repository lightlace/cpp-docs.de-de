---
title: "Agile::Agile-Konstruktor | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::Agile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::Agile"
ms.assetid: 33c1df82-f5db-4750-98cc-0daa03be4e59
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::Agile-Konstruktor
Initialisiert eine neue Instanz der Agile\-Klasse.  
  
## Syntax  
  
```cpp  
  
 Agile();  
  
Agile(T^ object);   
  
Agile(const Agile<T>& object);  
  
Agile(Agile<T>&& object);  
  
```  
  
#### Parameter  
 `T`  
 Ein Typ, der durch den Typnamenparameter der Vorlage spezifiziert wird.  
  
 `object`  
 In der zweiten Version dieses Konstruktors wird ein Objekt verwendet, um eine neue Agile\-Instanz zu initialisieren. In der dritten Version das Objekt, das zur neuen Agile\-Instanz kopiert wird. In der vierten Version das Objekt, das zur neuen Agile\-Instanz verschoben wird.  
  
## Hinweise  
 Die erste Version dieses Konstruktors ist der Standardkonstruktor. Die zweite Version initialisiert eine neue Agile\-Instanzklasse aus dem Objekt, das durch den `object`\-Parameter spezifiziert wird. Die dritte Version ist der Kopierkonstruktor. Die vierte Version ist der Verschiebungskonstruktor. Dieser Konstruktor kann keine Ausnahmen auslösen.  
  
## Anforderungen  
 **Unterstützter Client \(Mindestversion\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Mindestversion\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Header:** vccorlib.h  
  
## Siehe auch  
 [Platform::Agile\-Klasse](../cppcx/platform-agile-class.md)
---
title: "Agile::Release-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::Release"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::Release"
ms.assetid: aa825134-943f-425d-857e-449ec104765e
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::Release-Methode
Verwirft das Objekt und den Kontext, die dem aktuellen Agile\-Objekt zugrunde liegen.  
  
## Syntax  
  
```cpp  
  
void Release() throw();  
  
```  
  
## Hinweise  
 Das Objekt und der Kontext, die dem aktuellen Agile\-Objekt zugrunde liegen, werden verworfen, falls sie vorhanden sind. Anschließend wird der Wert des Agile\-Objekts auf Null gesetzt.  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Header:** vccorlib.h  
  
## Siehe auch  
 [Platform::Agile\-Klasse](../cppcx/platform-agile-class.md)
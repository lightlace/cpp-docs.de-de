---
title: "Agile::GetAddressOfForInOut-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::GetAddressOfForInOut"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::GetAddressOfForInOut"
ms.assetid: 8bb27b4c-c325-49ee-91db-9adf87c530c4
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::GetAddressOfForInOut-Methode
Gibt die Adresse eines Handles zum Objekt zurück, das vom aktuellen Agile\-Objekt dargestellt wird.  
  
## Syntax  
  
```cpp  
  
       T^* GetAddressOfForInOut()   
throw();  
  
```  
  
#### Parameter  
 `T`  
 Ein Typ, der durch den Typnamenparameter der Vorlage spezifiziert wird.  
  
## Rückgabewert  
 Die Adresse eines Handles zum Objekt, das vom aktuellen Agile\-Objekt dargestellt wird.  
  
## Hinweise  
 Durch diesen Vorgang wird der aktuelle Threadingkontext abgerufen und dann die Adresse eines Handles zum zugrunde liegenden Objekt zurückgegeben.  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Header:** vccorlib.h  
  
## Siehe auch  
 [Platform::Agile\-Klasse](../cppcx/platform-agile-class.md)
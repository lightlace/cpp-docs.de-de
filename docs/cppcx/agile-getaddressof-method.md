---
title: "Agile::GetAddressOf-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::GetAddressOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::GetAddressOf"
ms.assetid: f015edf9-4155-4992-a6fc-7ff1edcc5d1e
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::GetAddressOf-Methode
Initialisiert das aktuelle Agile\-Objekt neu und gibt dann die Adresse eines Handles für ein Objekt vom Typ `T` zurück.  
  
## Syntax  
  
```cpp  
  
       T^* GetAddressOf()   
throw();  
```  
  
#### Parameter  
 `T`  
 Ein Typ, der durch den Typnamenparameter der Vorlage spezifiziert wird.  
  
## Rückgabewert  
 Die Adresse eines Handles für ein Objekt des Typs `T`  
  
## Hinweise  
 Dieser Vorgang gibt die aktuelle Darstellung eines Objekts vom Typ `T` frei, sofern vorhanden. Dann werden die Datenmember des Agile\-Objekts initialisiert, der aktuelle Threadingkontext abgerufen und anschließend die Adresse einer handle\-to\-object\-Variablen zurückgegeben, die ein Nicht\-Agile\-Objekt darstellen kann. Wenn eine Agile\-Klasseninstanz ein Objekt darstellen soll, verwenden Sie den Zuweisungsoperator \([Agile::operator\=](../cppcx/agile-operator-assign-operator.md)\), um das Objekt zur Agile\-Klasseninstanz zuzuweisen.  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Header:** vccorlib.h  
  
## Siehe auch  
 [Platform::Agile\-Klasse](../cppcx/platform-agile-class.md)
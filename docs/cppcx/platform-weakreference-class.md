---
title: "Platform::WeakReference-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform::WeakReference"
ms.assetid: 8cfe1977-a8c7-4b7b-b539-25c77ed4c5f1
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::WeakReference-Klasse
Stellt einen schwachen Verweis auf eine Instanz einer Verweisklasse dar.  
  
## Syntax  
  
```vb  
class WeakReference  
```  
  
#### Parameter  
  
## Mitglieder  
  
### Konstruktoren  
  
|Member|Beschreibung|  
|------------|------------------|  
|[WeakReference::WeakReference\-Konstruktor](../cppcx/weakreference-weakreference-constructor-c-cx.md)|Initialisiert eine neue Instanz der WeakReference\-Klasse.|  
  
### Methoden  
  
|Member|Beschreibung|  
|------------|------------------|  
|[WeakReference::Resolve\-Methode](../cppcx/weakreference-resolve-method-platform-namespace.md)|Gibt einen Handle zur zugrunde liegenden Verweisklasse oder nullptr zurück, wenn das Objekt nicht mehr vorhanden ist.|  
  
### Operatoren  
  
|Member|Beschreibung|  
|------------|------------------|  
|[WeakReference::operator\=](../cppcx/weakreference-operator-assign.md)|Weist dem WeakReference\-Objekt einen neuen Wert zu.|  
  
## Hinweise  
 Die WeakReference\-Klasse selbst ist keine Verweisklasse und erbt daher nicht von Platform::Object^ und kann nicht in der Signatur einer öffentlichen Methode verwendet werden.  
  
## Siehe auch  
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)
---
title: "Object::GetHashCode-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Object::GetHashCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Plattform, Object::GetHashCode"
ms.assetid: 403a60e9-be1d-4702-b14d-27fa4b2a043b
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Object::GetHashCode-Methode
Gibt den [IUnknown](../atl/iunknown.md)\*\-Identitätswert für diese Instanz zurück, wenn es sich um ein COM\-Objekt handelt, bzw. einen berechneten Hashwert, wenn es kein COM\-Objekt ist.  
  
## Syntax  
  
```cpp  
public:int GetHashCode()  
```  
  
## Rückgabewert  
 Ein numerischer Wert, der das Objekt eindeutig identifiziert.  
  
## Hinweise  
 Sie können GetHashCode zum Erstellen von Schlüsseln für Objekte in Zuordnungen verwenden. Sie können Hashcodes mit [Object::Equals\-Methode](../cppcx/object-equals-method.md) vergleichen. Wenn der Codepfad äußerst wichtig ist und `GetHashCode` sowie `Equals` nicht schnell genug sind, können Sie auf die zugrunde liegende COM\-Ebene herunter wechseln und systemeigene [IUnknown](../atl/iunknown.md)\-Zeigervergleiche ausführen.  
  
## Anforderungen  
 **Unterstützter Client \(Mindestversion\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Mindestversion\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Header:** vccorlib.h  
  
## Siehe auch  
 [Platform::Object\-Klasse](../cppcx/platform-object-class.md)
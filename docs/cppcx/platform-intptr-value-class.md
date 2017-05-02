---
title: "Platform::IntPtr-Wertklasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IntPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::IntPtr-Struktur"
ms.assetid: 6c0326e8-edfd-4e53-a963-240b845dcde8
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::IntPtr-Wertklasse
Stellt einen Zeiger oder ein Handle mit Vorzeichen dar, dessen Größe plattformspezifisch ist \(32\-Bit oder 64\-Bit\).  
  
## Syntax  
  
```cpp  
public value struct IntPtr  
```  
  
## Mitglieder  
 IntPtr hat die folgenden Mitglieder:  
  
|Member|Beschreibung|  
|------------|------------------|  
|[IntPtr::IntPtr\-Konstruktor](../cppcx/intptr-intptr-constructor.md)|Initialisiert eine neue Instanz von IntPtr.|  
|[IntPtr::op\_explicit\-Operator](../cppcx/intptr-op-explicit-operator.md)|Konvertiert den angegebenen Parameter in einen IntPtr oder einen Zeiger auf einen IntPtr\-Wert.|  
|[IntPtr::ToInt32\-Methode](../cppcx/intptr-toint32-method.md)|Konvertiert den aktuellen IntPtr in eine 32\-Bit\-Ganzzahl.|  
  
## Anforderungen  
 **Unterstützter Client \(Mindestversion\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Mindestversion\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## Siehe auch  
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)
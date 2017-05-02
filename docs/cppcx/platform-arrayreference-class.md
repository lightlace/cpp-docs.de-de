---
title: "Platform::ArrayReference-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::ArrayReference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::ArrayReference-Klasse"
ms.assetid: 9ab3b15e-8a60-4600-8fcb-7d6c86284f4b
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::ArrayReference-Klasse
`ArrayReference` ist ein Optimierungstyp, den Sie als Ersatz für [Platform::Array^](../cppcx/platform-array-class.md) in den Eingabeparametern verwenden können, wenn Sie ein Array im C\-Format mit Eingabedaten füllen möchten.  
  
## Syntax  
  
```vb  
  
```  
  
```csharp  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[ArrayReference::ArrayReference\-Konstruktor](../cppcx/arrayreference-arrayreference-constructor.md)|Initialisiert eine neue Instanz der `ArrayReference`\-Klasse.|  
  
### Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[ArrayReference::operator\(\)\-Operator](../cppcx/arrayreference-operator-call-operator.md)|Konvertiert diesen `ArrayReference` in ein `Platform::Array<T>^*`\-Element.|  
|[ArrayReference::operator\=\-Operator](../cppcx/arrayreference-operator-assign-operator.md)|Weist dieser Instanz den Inhalt von einem anderen `ArrayReference` zu.|  
  
## Ausnahmen  
  
## Hinweise  
 Mit `ArrayReference` zum Auffüllen eines Arrays im C\-Format, vermeiden Sie den zusätzlichen Kopiervorgang, der dadurch aufgerufen würde, zunächst in eine `Platform::Array`\-Variable zu kopieren, und dann in einem zweiten Schritt in das Array im C\-Format. Bei Verwendung von `ArrayReference`, entsteht nur ein Kopiervorgang. Ein Codebeispiel finden Sie unter [Array und WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Header:** vccorlib.h  
  
## Überschrift für Unterabschnitt  
  
## Siehe auch  
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)
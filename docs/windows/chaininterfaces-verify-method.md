---
title: "ChainInterfaces::Verify-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::ChainInterfaces::Verify"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Verify-Methode"
ms.assetid: c591e130-8686-4130-ba69-1aaedc250038
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# ChainInterfaces::Verify-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Überprüft, ob jede Schnittstelle, der Vorlagenparameter `I0` mit `I9` definiert wird, von IUnknown und\/oder von IInspectable erbt und `I0` von `I1` durch `I9` erbt.  
  
## Syntax  
  
```  
WRL_NOTHROW __forceinline static void Verify();  
```  
  
## Hinweise  
 Wenn der `static_assert` Ausgaben Überprüfungsvorgang fehlschlägt, eine Fehlermeldung, die den Fehler beschreibt.  
  
## Hinweise  
 Vorlagenparameter `I0` und `I1` sind erforderlich, Parameter und `I2` von `I9` sind optional.  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [ChainInterfaces\-Struktur](../windows/chaininterfaces-structure.md)
---
title: "ActivationFactory::GetIids-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::ActivationFactory::GetIids"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetIids-Methode"
ms.assetid: 0983d709-d155-4d65-aae4-5b2c8bb0fede
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ActivationFactory::GetIids-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft ein Array implementierte Schnittstellen\-IDs ab.  
  
## Syntax  
  
```  
STDMETHOD(  
   GetIids  
)(_Out_ ULONG *iidCount, _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);  
```  
  
#### Parameter  
 `iidCount`  
 Wenn dieser Vorgang abgeschlossen ist, die Anzahl von interace IDs `iids` im Array.  
  
 `iids`  
 Wenn dieser Vorgang abgeschlossen ist, ein Array Schnittstellen\-IDs implementierte.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler beschreibt.  E\_OUTOFMEMORY ist ein beliebiges Fehler\-HRESULT.  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [ActivationFactory\-Klasse](../windows/activationfactory-class.md)
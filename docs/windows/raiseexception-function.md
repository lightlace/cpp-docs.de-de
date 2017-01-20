---
title: "RaiseException-Funktion"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "internal/Microsoft::WRL::Details::RaiseException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RaiseException-Funktion"
ms.assetid: f9c74f6d-112a-4d2e-900f-622f795d5dbf
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# RaiseException-Funktion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
inline void __declspec(noreturn)  
   RaiseException(  
      HRESULT hr,   
      DWORD dwExceptionFlags = EXCEPTION_NONCONTINUABLE);  
```  
  
#### Parameter  
 `hr`  
 Der Ausnahmecode der Ausnahme, die ausgelöst wird; das heißt, das HRESULT eines fehlgeschlagenen Vorgangs.  
  
 `dwExceptionFlags`  
 Ein Flag, das einer Ausnahme, die nicht zu einem Programmabbruch übergibt, angibt \(der Flagwert ist null\) oder nicht vernachlässigbare Ausnahme \(Flagwert ist ungleich 0 \(null\).  Standardmäßig wird die Ausnahme nicht vernachlässigbar.  
  
## Hinweise  
 Löst eine Ausnahme im aufrufenden Thread aus.  
  
 Weitere Informationen finden Sie die Funktion von **RaiseException**.  
  
## Anforderungen  
 **Header:**  internal.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)
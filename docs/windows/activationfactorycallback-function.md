---
title: "ActivationFactoryCallback-Funktion"
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
  - "module/Microsoft::WRL::Details::ActivationFactoryCallback"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActivationFactoryCallback-Funktion"
ms.assetid: dd40c79b-1273-4f2a-8c24-ae9926fb4fd9
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# ActivationFactoryCallback-Funktion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
inline HRESULT STDAPICALLTYPE ActivationFactoryCallback(  
   HSTRING activationId,  
   IActivationFactory **ppFactory  
);  
```  
  
#### Parameter  
 `activationId`  
 Handle einer Zeichenfolge, die einem Ablaufklassennamen angibt.  
  
 `ppFactory`  
 Wenn dieser Vorgang abgeschlossen wurde, eine Aktivierungsfactory, die an den `activationId`\- Parameter entspricht.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler beschreibt.  Wahrscheinliche Fehler\-HRESULT sind CLASS\_E\_CLASSNOTAVAILABLE und E\_INVALIDARG.  
  
## Hinweise  
 Ruft die Aktivierungsfactory für die angegebene Aktivierung ID ab  
  
 Die Runtime Windows ruft diese Rückruffunktion auf, um ein Objekt anfordern, das von den Ablaufklassennamen angegeben wird.  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)
---
title: "WeakReference::Resolve-Methode"
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
  - "implements/Microsoft::WRL::Details::WeakReference::Resolve"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Resolve-Methode"
ms.assetid: fc65a4b7-48a0-4d64-a793-37f566fdd8e7
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# WeakReference::Resolve-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
  
STDMETHOD(Resolve)  
   (REFIID riid,   
   _Deref_out_opt_ IInspectable **ppvObject  
);  
```  
  
#### Parameter  
 `riid`  
 Eine Schnittstelle ID  
  
 `ppvObject`  
 Wenn dieser Vorgang abgeschlossen wurde, eine Kopie des aktuellen starken Verweis, wenn der starke Verweiszähler nicht 0 ist.  
  
## Rückgabewert  
  
-   S\_OK, wenn der Vorgang erfolgreich ist und der starke Verweiszähler ist null.  Der `ppvObject`\-Parameter ist auf `nullptr` festgelegt.  
  
-   S\_OK, wenn der Vorgang erfolgreich ist und der starke Verweiszähler ist ungleich 0.  Der Parameter `ppvObject` ist auf den starken Verweis festgelegt.  
  
-   Andernfalls ist ein HRESULT, die den Grund dieser Vorgang angibt aus.  
  
## Hinweise  
 Legt den angegebenen Zeiger auf den aktuellen starken Verweiswert fest, ob der starke Verweiszähler nicht 0 ist.  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [WeakReference\-Klasse](../windows/weakreference-class1.md)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)
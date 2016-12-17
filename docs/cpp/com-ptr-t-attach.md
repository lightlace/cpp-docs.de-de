---
title: "_com_ptr_t::Attach"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "_com_ptr_t::Attach"
  - "_com_ptr_t.Attach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Attach-Methode"
  - "COM-Schnittstellen, attach-Zeiger"
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# _com_ptr_t::Attach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Kapselt einen unformatierten Schnittstellenzeiger vom Typ dieses intelligenten Zeigers.  
  
## Syntax  
  
```  
  
      void Attach(  
   Interface* pInterface   
) throw( );  
void Attach(  
   Interface* pInterface,  
   bool fAddRef   
) throw( );  
```  
  
#### Parameter  
 `pInterface`  
 Ein unformatierter Schnittstellenzeiger.  
  
 `fAddRef`  
 Wenn es **true** ist, wird `AddRef` aufgerufen.  Wenn es **false** hat, übernimmt das `_com_ptr_t`\-Objekt den Besitz des unformatierten Schnittstellenzeigers, ohne `AddRef` aufzurufen.  
  
## Hinweise  
  
-   **Attach\(**  `pInterface`  **\)** `AddRef` wird nicht aufgerufen.  Der Besitz der Schnittstelle wird an dieses `_com_ptr_t`\-Objekt übergeben.  **Release** wird aufgerufen, um den Verweiszähler für den zuvor gekapselten Zeiger zu verringern.  
  
-   **Attach\(**  `pInterface` **,**  `fAddRef`  **\)** Wenn `fAddRef` **true** ist, wird `AddRef`aufgerufen, um den Verweiszähler für den gekapselten Schnittstellenzeiger zu inkrementieren.  Wenn `fAddRef` **false** ist, übernimmt dieses `_com_ptr_t`\-Objekt den Besitz des unformatierten Schnittstellenzeigers, ohne `AddRef` aufzurufen.  **Release** wird aufgerufen, um den Verweiszähler für den zuvor gekapselten Zeiger zu verringern.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_com\_ptr\_t\-Klasse](../cpp/com-ptr-t-class.md)
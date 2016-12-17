---
title: "WeakRef::As-Methode"
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
  - "client/Microsoft::WRL::WeakRef::As"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "As-Methode"
ms.assetid: 7173da62-b3fe-44d6-aea4-1aa97e69b221
caps.latest.revision: 6
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# WeakRef::As-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Legt den angegebenen ComPtr\-Zeigerparameter so fest, dass er die angegebene Schnittstelle darstellt.  
  
## Syntax  
  
```  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ ComPtr<U>* ptr  
);  
  
template<  
   typename U  
>  
HRESULT As(  
   _Out_ Details::ComPtrRef<ComPtr<U>> ptr  
);  
```  
  
#### Parameter  
 `U`  
 Eine Schnittstellen\-ID.  
  
 `ptr`  
 Wenn dieser Vorgang abgeschlossen wird, ein Objekt das den Parameter `U` darstellt.  
  
## Rückgabewert  
  
-   S\_OK, wenn dieser Vorgang erfolgreich ausgeführt wurde; andernfalls ein HRESULT, das den Grund für den Fehler beim Vorgang angibt, und `ptr` wird auf `nullptr` festgelegt.  
  
-   S\_OK, wenn dieser Vorgang erfolgreich ausgeführt wurde, das aktuelle WeakRef\-Objekt aber bereits freigegeben wurde. Der `ptr`\-Parameter wird auf `nullptr` festgelegt.  
  
-   S\_OK, wenn dieser Vorgang erfolgreich ausgeführt wurde, das aktuelle WeakRef\-Objekt aber nicht vom Parameter `U` abgeleitet ist. Der `ptr`\-Parameter wird auf `nullptr` festgelegt.  
  
## Hinweise  
 Ein Fehler wird ausgegeben, wenn der Parameter `U` „IWeakReference“ ist oder nicht von „IInspectable“ abgeleitet ist.  
  
 Die erste Vorlage ist die Form, die Sie in Ihrem Code verwenden sollten. Die zweite Vorlage ist eine interne Hilfsspezialisierung, die C\+\+\-Sprachfeatures unterstützt, wie etwa das Schlüsselwort [auto](../cpp/auto-cpp.md) zur Typableitung.  
  
 Beginnend mit dem Windows 10 SDK legt diese Methode die WeakRef\-Instanz nicht auf `nullptr` fest, wenn der schwache Verweis nicht abgerufen werden konnte, daher sollten Sie Code zur Fehlerprüfung vermeiden, der WeakRef auf `nullptr` überprüft. Überprüfen Sie stattdessen das zurückgegebene HRESULT, um zu bestimmen, ob die Methode erfolgreich ausgeführt wurde, oder überprüfen Sie `ptr` auf `nullptr`.  
  
## Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [WeakRef\-Klasse](../windows/weakref-class.md)
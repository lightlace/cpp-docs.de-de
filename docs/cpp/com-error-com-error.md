---
title: "_com_error::_com_error"
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
  - "_com_error._com_error"
  - "_com_error::_com_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_com_error-Methode"
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::_com_error
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Erstellt ein `_com_error`\-Objekt.  
  
## Syntax  
  
```  
  
      _com_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = NULL,  
   bool fAddRef=false  
) throw( );  
_com_error(  
   const _com_error& that   
) throw( );  
```  
  
#### Parameter  
 `hr`  
 `HRESULT`\-Informationen.  
  
 `perrinfo`  
 **IErrorInfo**\-Objekt.  
  
 **bool fAddRef\=false**  
 Veranlasst den Konstruktor, AddRef auf einer Nicht\-NULL\-**IErrorInfo**\-Schnittstelle aufzurufen.  Dies ermöglicht eine richtige Verweiszählung im typischen Fall, in dem Besitz der Schnittstelle in das `_com_error`\-Objekt übergeben wird, wie z. B.:  
  
```  
throw _com_error(hr, perrinfo);  
```  
  
 Wenn Sie nicht möchten, dass der Code den Besitz an das `_com_error`\-Objekt überträgt, und wenn `AddRef` erforderlich ist, um **Release** im Destruktor `_com_error` zu versetzen, erstellen Sie das Objekt wie folgt:  
  
```  
_com_error err(hr, perrinfo, true);  
```  
  
 `that`  
 Ein vorhandenes `_com_error`\-Objekt.  
  
## Hinweise  
 Der erste Konstruktor erstellt ein neues Objekt, das ein `HRESULT`\- und ein optionales **IErrorInfo**\-Objekt erhält.  Der zweite Konstruktor erstellt eine Kopie eines vorhandenen `_com_error`\-Objekts.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_com\_error\-Klasse](../cpp/com-error-class.md)
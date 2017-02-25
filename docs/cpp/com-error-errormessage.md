---
title: "_com_error::ErrorMessage | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error::ErrorMessage"
  - "_com_error.ErrorMessage"
  - "ErrorMessage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ErrorMessage-Methode"
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::ErrorMessage
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ruft die Zeichenfolgenmeldung für das `HRESULT`\-Objekt ab, das im `_com_error`\-Objekt gespeichert ist.  
  
## Syntax  
  
```  
  
const TCHAR * ErrorMessage( ) const throw( );  
  
```  
  
## Rückgabewert  
 Gibt die Zeichenfolgenmeldung für das `HRESULT`\-Objekt zurück, das innerhalb des `_com_error`\-Objekts aufgezeichnet wird.  Wenn `HRESULT` ein zugeordneter 16\-Bit\-[wCode](../cpp/com-error-wcode.md) ist, wird eine generische Meldung "`IDispatch error #<wCode>`" zurückgegeben.  Wenn keine Nachricht gefunden wird, wird eine generische Meldung "`Unknown error #<hresult>`" zurückgegeben.  Die zurückgegebene Zeichenfolge ist entweder eine Unicode\- oder eine Multibyte\-Zeichenfolge, abhängig vom Zustand des **\_UNICODE**\-Makros.  
  
## Hinweise  
 Ruft den entsprechenden Systemnachrichtentext für das `HRESULT`\-Objekt ab, das innerhalb des `_com_error`\-Objekts erfasst ist.  Der Systemnachrichtentext wird durch Aufruf der Win32\-[FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351)\-Funktion abgerufen.  Die zurückgegebene Zeichenfolge wird von der `FormatMessage`\-API zugeordnet und wird ausgegeben, wenn das `_com_error`\-Objekt zerstört wird.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_com\_error\-Klasse](../cpp/com-error-class.md)
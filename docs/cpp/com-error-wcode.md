---
title: "_com_error::WCode"
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
  - "_com_error.WCode"
  - "_com_error::WCode"
  - "WCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WCode-Methode"
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::WCode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ruft den 16\-Bit\-Fehlercode ab, der dem gekapselten `HRESULT` zugeordnet ist.  
  
## Syntax  
  
```  
  
WORD WCode ( ) const throw( );  
  
```  
  
## Rückgabewert  
 Wenn `HRESULT` innerhalb des Bereichs 0x80040200 bis 0x8004FFFF liegt, gibt die **WCode**\-Methode `HRESULT` minus 0x80040200 zurück; andernfalls 0 \(null\).  
  
## Hinweise  
 Die **WCode**\-Methode wird verwendet, um eine Zuordnung rückgängig zu machen, die im COM\-Unterstützungscode vorgenommen wird.  Der Wrapper für eine **dispinterface**\-Eigenschaft oder \-Methode ruft eine Unterstützungsroutine auf, die die Argumente verpackt und **IDispatch::Invoke** aufruft.  Wenn ein Fehler `HRESULT` `DISP_E_EXCEPTION` zurückgegeben wird, werden die Fehlerinformationen nach der Rückgabe aus der **EXCEPINFO**\-Struktur abgerufen, die an **IDispatch::Invoke** übergeben wurde.  Der Fehlercode kann entweder ein 16\-Bit\-Wert sein, der im Member `wCode` der Struktur **EXCEPINFO** gespeichert ist oder ein vollständiger 32\-bit\-Wert im Member **scode** der Struktur **EXCEPINFO**.  Wenn ein 16\-Bit\-`wCode` zurückgegeben wird, muss er zuerst einem 32\-Bit\-Fehler\-`HRESULT` zugeordnet werden.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_com\_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [\_com\_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [\_com\_error\-Klasse](../cpp/com-error-class.md)
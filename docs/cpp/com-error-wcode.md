---
title: '_com_error:: wcode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::WCode
dev_langs: C++
helpviewer_keywords: WCode method [C++]
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 74f79491b9d4f88e19bcd0f7a20c94b26d0f7909
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="comerrorwcode"></a>_com_error::WCode
**Microsoft-spezifisch**  
  
 Ruft den 16-Bit-Fehlercode ab, der dem gekapselten `HRESULT` zugeordnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
WORD WCode ( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn die `HRESULT` innerhalb des Bereichs 0 x 80040200 bis 0x8004ffff liegt, wird die **WCode** Methode gibt die `HRESULT` minus 0 x 80040200; zurückgegeben, andernfalls 0 (null).  
  
## <a name="remarks"></a>Hinweise  
 Die **WCode** Methode wird verwendet, um eine Zuordnung rückgängig zu machen, die in der COM-Unterstützungscode vorgenommen wird. Der Wrapper für eine **Dispinterface** -Eigenschaft oder-Methode ruft eine unterstützungsroutine auf, die die Argumente und Aufrufe verpackt **IDispatch:: Invoke**. Nach der Rückgabe bei einem Fehler `HRESULT` von `DISP_E_EXCEPTION` zurückgegeben wird, wird die Fehlerinformationen abgerufen, von der **EXCEPINFO** Struktur übergeben, um **IDispatch:: Invoke**. Der Fehlercode kann entweder einem 16-Bit-Wert in der `wCode` Mitglied der **EXCEPINFO** Struktur- oder einen 32-Bit-Wert in der **Scode** Mitglied der **EXCEPINFO**Struktur. Wenn ein 16-Bit-`wCode` zurückgegeben wird, muss er zuerst einem 32-Bit-Fehler-`HRESULT` zugeordnet werden.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [_com_error-Klasse](../cpp/com-error-class.md)
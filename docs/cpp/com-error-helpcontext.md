---
title: _com_error::HelpContext | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::HelpContext
dev_langs: C++
helpviewer_keywords: HelpContext method [C++]
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d7c350a2c8879ecf927974aa48650c59247716c4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="comerrorhelpcontext"></a>_com_error::HelpContext
**Microsoft-spezifisch**  
  
 Aufrufe **IErrorInfo:: GetHelpContext** Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
DWORD HelpContext( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt das Ergebnis der **IErrorInfo:: GetHelpContext** für die **IErrorInfo** -Objekt erfasst wird, innerhalb der `_com_error` Objekt. Wenn kein **IErrorInfo** -Objekt erfasst wird, wird 0 zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Jeder Fehler beim Aufrufen der **IErrorInfo:: GetHelpContext** -Methode wird ignoriert.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_error-Klasse](../cpp/com-error-class.md)
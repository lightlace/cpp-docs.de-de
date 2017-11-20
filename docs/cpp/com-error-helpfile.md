---
title: _com_error::HelpFile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_error::HelpFile
dev_langs: C++
helpviewer_keywords: HelpFile method [C++]
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8b29120a15af3a494ad2a755f83342b3a6b83908
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="comerrorhelpfile"></a>_com_error::HelpFile
**Microsoft-spezifisch**  
  
 Aufrufe **IErrorInfo:: GetHelpFile** Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
_bstr_t HelpFile() const;  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt das Ergebnis der **IErrorInfo:: GetHelpFile** für die **IErrorInfo** -Objekt erfasst wird, innerhalb der `_com_error` Objekt. Das resultierende BSTR wird in einem `_bstr_t`-Objekt gekapselt. Wenn kein **IErrorInfo** wird aufgezeichnet, es gibt ein leeres `_bstr_t`.  
  
## <a name="remarks"></a>Hinweise  
 Jeder Fehler beim Aufrufen der **IErrorInfo:: GetHelpFile** -Methode wird ignoriert.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_error-Klasse](../cpp/com-error-class.md)
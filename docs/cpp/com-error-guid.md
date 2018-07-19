---
title: _com_error::GUID | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::GUID
dev_langs:
- C++
helpviewer_keywords:
- GUID method [C++]
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e324a84a16874a7e33f8687943b1302fbdd73a7a
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939025"
---
# <a name="comerrorguid"></a>_com_error::GUID
**Microsoft-spezifisch**  
  
 Ruft die `IErrorInfo::GetGUID`-Funktion auf.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
GUID GUID( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt das Ergebnis des `IErrorInfo::GetGUID` für die `IErrorInfo` -Objekt erfasst wird, innerhalb der `_com_error` Objekt. Wenn kein `IErrorInfo` -Objekt erfasst wird, gibt Sie GUID_NULL zurück.  
  
## <a name="remarks"></a>Hinweise  
 Jeder Fehler beim Aufrufen der `IErrorInfo::GetGUID` -Methode wird ignoriert.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_error-Klasse](../cpp/com-error-class.md)
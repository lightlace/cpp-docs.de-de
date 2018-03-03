---
title: _com_error::_com_error | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_error::_com_error
dev_langs:
- C++
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: df04357afd35b546fb43c90a102b7dc0cacdc95e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="comerrorcomerror"></a>_com_error::_com_error
**Microsoft-spezifisch**  
  
 Erstellt ein `_com_error`-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 `hr`  
 `HRESULT`-Informationen.  
  
 `perrinfo`  
 **IErrorInfo** Objekt.  
  
 **Bool fAddRef = "false"**  
 Veranlasst den Konstruktor, AddRef auf einer nicht-Null Aufrufen **IErrorInfo** Schnittstelle. Dies ermöglicht eine richtige Verweiszählung im typischen Fall, in dem Besitz der Schnittstelle in das `_com_error`-Objekt übergeben wird, wie z. B.:  
  
```  
throw _com_error(hr, perrinfo);  
```  
  
 Wenn Sie nicht möchten, dass Ihr Code zum Übertragen des Besitzes auf die `_com_error` -Objekt, und die `AddRef` ist erforderlich, um den offset der **Version** in der `_com_error` Destruktor, erstellen Sie das Objekt wie folgt:  
  
```  
_com_error err(hr, perrinfo, true);  
```  
  
 `that`  
 Ein vorhandenes `_com_error`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Der erste Konstruktor erstellt ein neues Objekt erhält eine `HRESULT` und optionale **IErrorInfo** Objekt. Der zweite Konstruktor erstellt eine Kopie eines vorhandenen `_com_error`-Objekts.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_error-Klasse](../cpp/com-error-class.md)
---
title: _com_error::_com_error | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::_com_error
dev_langs:
- C++
helpviewer_keywords:
- _com_error method [C++]
ms.assetid: 0a69e46c-caab-49ef-b091-eee401253ce6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec16faa9881fc1c69dca5f8f39b8797cf0fcff0d
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943508"
---
# <a name="comerrorcomerror"></a>_com_error::_com_error
**Microsoft-spezifisch**  
  
 Erstellt ein `_com_error`-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
_com_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = NULL,  
   bool fAddRef=false) throw( );  

_com_error( const _com_error& that ) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 *HR*  
 HRESULT-Informationen.  
  
 *perrinfo*  
 `IErrorInfo`-Objekt  
  
 `bool fAddRef=false`  
 Veranlasst den Konstruktor, AddRef auf einer nicht-Null Aufrufen `IErrorInfo` Schnittstelle. Dies ermöglicht eine richtige Verweiszählung im typischen Fall, in dem Besitz der Schnittstelle in das `_com_error`-Objekt übergeben wird, wie z. B.:  
  
```cpp 
throw _com_error(hr, perrinfo);  
```  
  
 Wenn Sie nicht möchten, dass Ihr Code zum Übertragen des Besitzes zu der `_com_error` -Objekt, und die `AddRef` ist erforderlich, um den offset der `Release` in die `_com_error` Destruktor, erstellen Sie wie folgt auf das Objekt:  
  
```cpp 
_com_error err(hr, perrinfo, true);  
```  
  
 *,*  
 Ein vorhandenes `_com_error`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Der erste Konstruktor erstellt ein neues Objekt angegeben wird, ein HRESULT und optionalen `IErrorInfo` Objekt. Der zweite Konstruktor erstellt eine Kopie eines vorhandenen `_com_error`-Objekts.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_error-Klasse](../cpp/com-error-class.md)
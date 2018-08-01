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
ms.openlocfilehash: c1389635c3ef026e8b3a7dfe13976cca58a15a82
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406717"
---
# <a name="comerrorcomerror"></a>_com_error::_com_error
**Microsoft-spezifisch**  
  
 Erstellt eine **_com_error** Objekt.  
  
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
 Veranlasst den Konstruktor, AddRef auf einer nicht-Null Aufrufen `IErrorInfo` Schnittstelle. Dadurch wird eine richtige verweiszählung im typischen Fall, in dem Besitz der Schnittstelle übergeben wird, die **_com_error** Objekt, z. B.:  
  
```cpp 
throw _com_error(hr, perrinfo);  
```  
  
 Wenn Sie nicht möchten, dass Ihr Code zum Übertragen des Besitzes zu der **_com_error** -Objekt, und die `AddRef` ist erforderlich, um den offset der `Release` in die **_com_error** Destruktor, erstellen Sie das Objekt als Die folgende:  
  
```cpp 
_com_error err(hr, perrinfo, true);  
```  
  
 *,*  
 Eine vorhandene **_com_error** Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Der erste Konstruktor erstellt ein neues Objekt angegeben wird, ein HRESULT und optionalen `IErrorInfo` Objekt. Der zweite Konstruktor erstellt eine Kopie eines vorhandenen **_com_error** Objekt.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_com_error-Klasse](../cpp/com-error-class.md)
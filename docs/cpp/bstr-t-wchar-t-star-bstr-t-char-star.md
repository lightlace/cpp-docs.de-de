---
title: _bstr_t::wchar_t *, _bstr_t::char* | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::wchar_t*
- _bstr_t::char*
dev_langs:
- C++
helpviewer_keywords:
- operator wchar_t* [C++]
- operator char* [C++]
ms.assetid: acd9f4a7-b427-42c2-aaae-acae21cab317
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ebe1f3ad7b0fc46e1edba013f4cc986f1771972d
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39409145"
---
# <a name="bstrtwchart-bstrtchar"></a>_bstr_t::wchar_t *, _bstr_t::char*
**Microsoft-spezifisch**  
  
 Gibt die BSTR-Zeichen als Array von schmalen oder breiten Zeichen zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
operator const wchar_t*( ) const throw( );   
operator wchar_t*( ) const throw( );   
operator const char*( ) const;   
operator char*( ) const;  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Operatoren können verwendet werden, um die Zeichendaten zu extrahieren, die vom `BSTR`-Objekt gekapselt werden. Durch die Zuweisung eines neuen Werts zum zurückgegebenen Zeiger werden die ursprünglichen BSTR-Daten nicht geändert.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [_bstr_t-Klasse](../cpp/bstr-t-class.md)
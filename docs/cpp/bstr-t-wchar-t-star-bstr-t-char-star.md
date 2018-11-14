---
title: _bstr_t::wchar_t *, _bstr_t::char*
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::wchar_t*
- _bstr_t::char*
helpviewer_keywords:
- operator wchar_t* [C++]
- operator char* [C++]
ms.assetid: acd9f4a7-b427-42c2-aaae-acae21cab317
ms.openlocfilehash: bfc149b0f0688bed567bf202fddb4ab2c3102630
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51325808"
---
# <a name="bstrtwchart-bstrtchar"></a>_bstr_t::wchar_t\*, _bstr_t::char\*

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
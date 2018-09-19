---
title: +=,-_bstr_t::Operator + | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::operator+
- _bstr_t::operator+=
dev_langs:
- C++
helpviewer_keywords:
- += operator [C++], appending strings
- + operator [C++], _bstr_t objects
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a440e8b8d078c7849de2a0b29f1d50b140d70070
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044768"
---
# <a name="bstrtoperator--"></a>_bstr_t::operator +=, +

**Microsoft-spezifisch**

Fügt Zeichen am Ende des `_bstr_t`-Objekts hinzu oder verkettet zwei Zeichenfolgen.

## <a name="syntax"></a>Syntax

```
_bstr_t& operator+=( const _bstr_t& s1 );
_bstr_t operator+( const _bstr_t& s1 );
friend _bstr_t operator+( const char* s2, const _bstr_t& s1);
friend _bstr_t operator+( const wchar_t* s3, const _bstr_t& s1);
```

#### <a name="parameters"></a>Parameter

*s1*<br/>
Ein `_bstr_t`-Objekt.

*s2*<br/>
Eine Mehrbytezeichenfolge.

*s3*<br/>
Eine Unicode-Zeichenfolge.

## <a name="remarks"></a>Hinweise

Diese Operatoren führen eine Zeichenfolgenverkettung aus:

- **Operator += (***s1***)** fügt die Zeichen im gekapselten `BSTR` von *s1* am Ende dieses Objekts gekapselten `BSTR`.

- **Operator + (***s1***)** gibt die neue `_bstr_t` sein, der durch die Verkettung dieses Objekts `BSTR` mit dem *s1*.

- **Operator + (***s2***&#124;***s1***)** gibt ein neues `_bstr_t` sein, der durch die Verkettung ein Multibyte-Zeichenfolge *s2*, umgewandelt in Unicode, mit der `BSTR` in gekapselt *s1*.

- **Operator + (***s3* **,***s1***)** gibt ein neues `_bstr_t` sein, der durch die Verkettung einer Unicode-Zeichenfolge *s3* mit der `BSTR` in gekapselt *s1*.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_bstr_t-Klasse](../cpp/bstr-t-class.md)
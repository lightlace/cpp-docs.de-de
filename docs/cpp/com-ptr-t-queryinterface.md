---
title: _com_ptr_t::QueryInterface | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e0add1d8f3fc73f78cee3e10642d7b5a12968a6a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106871"
---
# <a name="comptrtqueryinterface"></a>_com_ptr_t::QueryInterface

**Microsoft-spezifisch**

Ruft die **QueryInterface** Memberfunktion `IUnknown` für den gekapselten Schnittstellenzeiger auf.

## <a name="syntax"></a>Syntax

```
template<typename _InterfaceType> HRESULT QueryInterface (
   const IID& iid,
   _InterfaceType*& p
) throw ( );
template<typename _InterfaceType> HRESULT QueryInterface (
   const IID& iid,
   _InterfaceType** p
) throw( );
```

#### <a name="parameters"></a>Parameter

*IID*<br/>
`IID` eines Schnittstellenzeigers.

*p*<br/>
Nicht formatierter Schnittstellenzeiger.

## <a name="remarks"></a>Hinweise

Aufrufe `IUnknown::QueryInterface` für den gekapselten Schnittstellenzeiger mit dem angegebenen `IID` und gibt den resultierenden unformatierten Schnittstellenzeiger in *p*. Diese Routine gibt zurück, das HRESULT, um den Erfolg oder Fehler anzuzeigen.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)
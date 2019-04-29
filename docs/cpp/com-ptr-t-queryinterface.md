---
title: _com_ptr_t::QueryInterface
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
helpviewer_keywords:
- QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
ms.openlocfilehash: 42953c92e4cf31b5ccd02dd51811fc1fdeedbcaf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399277"
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

*iid*<br/>
`IID` eines Schnittstellenzeigers.

*p*<br/>
Nicht formatierter Schnittstellenzeiger.

## <a name="remarks"></a>Hinweise

Aufrufe `IUnknown::QueryInterface` für den gekapselten Schnittstellenzeiger mit dem angegebenen `IID` und gibt den resultierenden unformatierten Schnittstellenzeiger in *p*. Diese Routine gibt zurück, das HRESULT, um den Erfolg oder Fehler anzuzeigen.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)
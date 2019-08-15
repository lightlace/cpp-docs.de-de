---
title: _com_ptr_t::GetActiveObject
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::GetActiveObject
helpviewer_keywords:
- GetActiveObject method [C++]
ms.assetid: 2fa94853-0410-4620-91f2-136dae923f9f
ms.openlocfilehash: f13a42878392f63096cdfcb405f3f91cc0efe451
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498895"
---
# <a name="_com_ptr_tgetactiveobject"></a>_com_ptr_t::GetActiveObject

**Microsoft-spezifisch**

Hängt an eine vorhandene Instanz eines-Objekts an, `CLSID` Wenn `ProgID`ein oder ein angegeben wird.

## <a name="syntax"></a>Syntax

```
HRESULT GetActiveObject(
   const CLSID& rclsid
) throw( );
HRESULT GetActiveObject(
   LPCWSTR clsidString
) throw( );
HRESULT GetActiveObject(
   LPCSTR clsidStringA
) throw( );
```

#### <a name="parameters"></a>Parameter

*rclsid*<br/>
Der `CLSID` eines Objekts.

*clsidString*<br/>
Eine Unicode-Zeichenfolge, die `CLSID` entweder eine (beginnend mit " **{** `ProgID`") oder enthält.

*clsidStringA*<br/>
Eine Multibytezeichenfolge, die die ANSI-Codepage verwendet `CLSID` , die entweder eine (beginnend mit " **{** ") oder eine `ProgID`enthält.

## <a name="remarks"></a>Hinweise

Diese Member-Funktionen rufen **GetActiveObject** auf, um einen Zeiger auf ein aktuell registriertes Objekt abzurufen, das bei OLE registriert wurde, und dann Abfragen für den Schnittstellentyp dieses intelligenten Zeigers. Das Zeigerergebnis wird dann innerhalb dieses `_com_ptr_t`-Objekts gekapselt. `Release`wird aufgerufen, um den Verweis Zähler für den zuvor gekapselten Zeiger zu verringern. Diese Routine gibt das HRESULT zurück, um einen Erfolg oder Fehler anzugeben.

- **GetActiveObject (** `rclsid` **)** wird an eine vorhandene Instanz `CLSID`eines Objekts angefügt.

- **GetActiveObject (** `clsidString` **)** wird an eine vorhandene Instanz eines Objekts angehängt, wenn eine Unicode-Zeichenfolge vorhanden `CLSID` ist, die entweder einen (beginnend mit " `ProgID` **{** ") oder eine enthält.

- **GetActiveObject (** `clsidStringA` **)** wird an eine vorhandene Instanz eines Objekts angehängt, wenn eine Multibytezeichenfolge angegeben `CLSID` wird, die entweder einen (beginnend mit " `ProgID` **{** ") oder eine enthält. Ruft [multibytedewidechar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)auf, bei dem davon ausgegangen wird, dass die Zeichenfolge in der ANSI-Codepage statt in einer OEM-Codepage ist.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)
---
title: _com_ptr_t::CreateInstance
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::CreateInstance
helpviewer_keywords:
- CreateInstance method [C++]
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
ms.openlocfilehash: 82b180b3f40683495ed2cfa284bdae8e1afaef9e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498661"
---
# <a name="_com_ptr_tcreateinstance"></a>_com_ptr_t::CreateInstance

**Microsoft-spezifisch**

Erstellt eine neue Instanz eines-Objekts, wenn `CLSID` ein `ProgID`oder ein angegeben wird.

## <a name="syntax"></a>Syntax

```
HRESULT CreateInstance(
   const CLSID& rclsid,
   IUnknown* pOuter=NULL,
   DWORD dwClsContext = CLSCTX_ALL
) throw( );
HRESULT CreateInstance(
   LPCWSTR clsidString,
   IUnknown* pOuter=NULL,
   DWORD dwClsContext = CLSCTX_ALL
) throw( );
HRESULT CreateInstance(
   LPCSTR clsidStringA,
   IUnknown* pOuter=NULL,
   DWORD dwClsContext = CLSCTX_ALL
) throw( );
```

#### <a name="parameters"></a>Parameter

*rclsid*<br/>
Der `CLSID` eines Objekts.

*clsidString*<br/>
Eine Unicode-Zeichenfolge, die `CLSID` entweder eine (beginnend mit " **{** `ProgID`") oder enthält.

*clsidStringA*<br/>
Eine Multibytezeichenfolge, die die ANSI-Codepage verwendet `CLSID` , die entweder eine (beginnend mit " **{** ") oder eine `ProgID`enthält.

*dwClsContext*<br/>
Kontext für die Ausführung von ausführbarem Code.

*pOuter*<br/>
Das äußere unbekannte für die [Aggregation](../atl/aggregation.md).

## <a name="remarks"></a>Hinweise

Diese Memberfunktionen rufen `CoCreateInstance` auf, um ein neues COM-Objekt zu erstellen, und fragen dann den Schnittstellentyp dieses intelligenten Zeigers ab. Das Zeigerergebnis wird dann innerhalb dieses `_com_ptr_t`-Objekts gekapselt. `Release`wird aufgerufen, um den Verweis Zähler für den zuvor gekapselten Zeiger zu verringern. Diese Routine gibt das HRESULT zurück, um einen Erfolg oder Fehler anzugeben.

- **CreateInstance (**  *Rclsid* **,**  *DwClsContext*  **)** erstellt eine neue ausgeführte Instanz eines Objekts, dem ein `CLSID`.

- **CreateInstance (**  *ClsidString* **,**  *DwClsContext* **)** erstellt eine neue ausgeführte Instanz eines angegebenen Objekts an eine Unicode-Zeichenfolge, die entweder eine `CLSID` (beginnend mit " **{** ") oder ein `ProgID`.

- **CreateInstance (**  *ClsidStringA* **,**  *DwClsContext*  **)** erstellt eine neue ausgeführte Instanz eines angegebenen Objekts an eine Multibyte-Zeichenfolge, die entweder eine `CLSID` (beginnend mit " **{** ") oder ein `ProgID`. Ruft [multibytedewidechar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)auf, bei dem davon ausgegangen wird, dass die Zeichenfolge in der ANSI-Codepage statt in einer OEM-Codepage ist.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)
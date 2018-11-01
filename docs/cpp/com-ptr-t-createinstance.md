---
title: _com_ptr_t::CreateInstance
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::CreateInstance
helpviewer_keywords:
- CreateInstance method [C++]
ms.assetid: ab89b0e1-9da3-4784-a079-58b17340f111
ms.openlocfilehash: c4f6cd54b90ab5fab69f91df67a8bf60b0b658f8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637462"
---
# <a name="comptrtcreateinstance"></a>_com_ptr_t::CreateInstance

**Microsoft-spezifisch**

Erstellt eine neue Instanz eines angegebenen Objekts an eine `CLSID` oder `ProgID`.

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
Die `CLSID` eines Objekts.

*clsidString*<br/>
Eine Unicode-Zeichenfolge, die entweder eine `CLSID` (beginnend mit "**{**") oder ein `ProgID`.

*clsidStringA*<br/>
Eine mehrbytezeichenfolge mit der ANSI-Codepage, die entweder eine `CLSID` (beginnend mit "**{**") oder ein `ProgID`.

*dwClsContext*<br/>
Kontext für die Ausführung von ausführbarem Code.

*pOuter*<br/>
Die äußere unbekannte für [Aggregation](../atl/aggregation.md).

## <a name="remarks"></a>Hinweise

Diese Memberfunktionen rufen `CoCreateInstance` auf, um ein neues COM-Objekt zu erstellen, und fragen dann den Schnittstellentyp dieses intelligenten Zeigers ab. Das Zeigerergebnis wird dann innerhalb dieses `_com_ptr_t`-Objekts gekapselt. `Release` wird aufgerufen, um den Verweiszähler für den zuvor gekapselten Zeiger zu verringern. Diese Routine gibt zurück, das HRESULT, um den Erfolg oder Fehler anzuzeigen.

- **CreateInstance (**  *Rclsid* **,**  *DwClsContext*  **)** erstellt eine neue ausgeführte Instanz eines Objekts, dem ein `CLSID`.

- **CreateInstance (**  *ClsidString* **,**  *DwClsContext* **)** erstellt eine neue ausgeführte Instanz eines angegebenen Objekts an eine Unicode-Zeichenfolge, die entweder eine `CLSID` (beginnend mit "**{**") oder ein `ProgID`.

- **CreateInstance (**  *ClsidStringA* **,**  *DwClsContext*  **)** erstellt eine neue ausgeführte Instanz eines angegebenen Objekts an eine Multibyte-Zeichenfolge, die entweder eine `CLSID` (beginnend mit "**{**") oder ein `ProgID`. Aufrufe [MultiByteToWideChar](/windows/desktop/api/stringapiset/nf-stringapiset-multibytetowidechar), dem wird davon ausgegangen, dass die Zeichenfolge in die ANSI-Codepage anstatt eine OEM-Codepage.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)
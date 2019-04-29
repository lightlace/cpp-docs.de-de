---
title: RDX (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.rdx
helpviewer_keywords:
- rdx attribute
ms.assetid: ff8e4312-c1ad-4934-bdaa-86f54409651e
ms.openlocfilehash: 2790c3de01d21242daee73fc442ad22d88739355
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407496"
---
# <a name="rdx"></a>rdx

Erstellt einen Registrierungsschlüssel oder ändert einen vorhandenen Registrierungsschlüssel.

## <a name="syntax"></a>Syntax

```cpp
[ rdx(key, valuename=NULL, regtype) ]
```

### <a name="parameters"></a>Parameter

*key*<br/>
Der Name des Schlüssels erstellt oder geöffnet werden.

*valuename*<br/>
(Optional) Gibt das Wertfeld "festgelegt werden. Wenn ein Wertfeld mit diesem Namen im Schlüssel nicht bereits vorhanden ist, wird sie hinzugefügt.

*regtype*<br/>
Der Typ des Registrierungsschlüssels, der hinzugefügt wird. Kann einen der folgenden sein: `text`, `dword`, `binary`, oder `CString`.

## <a name="remarks"></a>Hinweise

Die **Rdx** C++-Attribut erstellt oder ändert einen vorhandenen Registrierungsschlüssel für eine COM-Komponente. Das Attribut wird das Objekt, das den Zielmember implementiert ein Makro BEGIN_RDX_MAP hinzugefügt. `RegistryDataExchange`, eine Funktion, die durch das Makro BEGIN_RDX_MAP eingefügt dienen zum Übertragen von Daten zwischen der Registrierung und die Datenelemente

Dieses Attribut kann verwendet werden, in Verbindung mit der [Co-Klasse](coclass.md), [progid](progid.md), oder [Vi_progid](vi-progid.md) Attribute oder andere Attribute, die eines der genannten impliziert.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse** oder **Struktur** Member|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="example"></a>Beispiel

Der folgende Code Fügt einen Registrierungsschlüssel namens MyValue an das System die CMyClass COM-Komponente beschreiben.

```cpp
// cpp_attr_ref_rdx.cpp
// compile with: /LD /link /OPT:NOREF
#define _ATL_ATTRIBUTES
#include "atlbase.h"

[module (name="MyLib")];

class CMyClass {
public:
   CMyClass() {
      strcpy_s(m_sz, "SomeValue");
   }

   [ rdx(key = "HKCR\\MyApp.MyApp.1", valuename = "MyValue", regtype = "text")]
   char m_sz[256];
};
```

## <a name="see-also"></a>Siehe auch

[COM-Attribute](com-attributes.md)<br/>
[registration_script](registration-script.md)
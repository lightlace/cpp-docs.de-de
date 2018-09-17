---
title: RDX | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.rdx
dev_langs:
- C++
helpviewer_keywords:
- rdx attribute
ms.assetid: ff8e4312-c1ad-4934-bdaa-86f54409651e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 00ef28954a686dac72c8b7f55b86c88313e74643
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45719719"
---
# <a name="rdx"></a>rdx

Erstellt einen Registrierungsschlüssel oder ändert einen vorhandenen Registrierungsschlüssel.

## <a name="syntax"></a>Syntax

```cpp
[ rdx(
   key,
   valuename=NULL,
   regtype
) ]
```

### <a name="parameters"></a>Parameter

*key*  
Der Name des Schlüssels erstellt oder geöffnet werden.

*Wertname*  
(Optional) Gibt das Wertfeld "festgelegt werden. Wenn ein Wertfeld mit diesem Namen im Schlüssel nicht bereits vorhanden ist, wird sie hinzugefügt.

*regtype*  
Der Typ des Registrierungsschlüssels, der hinzugefügt wird. Kann einen der folgenden sein: `text`, `dword`, `binary`, oder `CString`.

## <a name="remarks"></a>Hinweise

Die **Rdx** C++-Attribut erstellt oder ändert einen vorhandenen Registrierungsschlüssel für eine COM-Komponente. Das Attribut wird das Objekt, das den Zielmember implementiert ein Makro BEGIN_RDX_MAP hinzugefügt. `RegistryDataExchange`, eine Funktion, die durch das Makro BEGIN_RDX_MAP eingefügt dienen zum Übertragen von Daten zwischen der Registrierung und die Datenelemente

Dieses Attribut kann verwendet werden, in Verbindung mit der [Co-Klasse](../windows/coclass.md), [progid](../windows/progid.md), oder [Vi_progid](../windows/vi-progid.md) Attribute oder andere Attribute, die eines der genannten impliziert.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse** oder **Struktur** Member|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

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

[COM-Attribute](../windows/com-attributes.md)  
[registration_script](../windows/registration-script.md)  
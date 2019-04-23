---
title: Co-Klasse (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.coclass
helpviewer_keywords:
- coclass attribute
ms.assetid: 42da6a10-3af9-4b43-9a1d-689d00b61eb3
ms.openlocfilehash: e1f99a2780ab4f451533a3e797e473f60680c6ab
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59035201"
---
# <a name="coclass"></a>coclass

Erstellt ein COM-Objekt, die eine COM-Schnittstelle implementieren können.

## <a name="syntax"></a>Syntax

```cpp
[coclass]
```

## <a name="remarks"></a>Hinweise

Die **Co-Klasse** C++-Attribut wird ein Co-Klasse-Konstrukt in der generierten IDL-Datei.

Wenn Sie eine Co-Klasse zu definieren, können Sie auch angeben der [Uuid](uuid-cpp-attributes.md), [Version](version-cpp.md), [threading](threading-cpp.md), [Vi_progid](vi-progid.md), und [progid ](progid.md) Attribute. Wenn eines dieser Projekte nicht angegeben ist, wird er erstellt werden.

Wenn zwei Headerdateien Klassen mit enthalten die **Co-Klasse** Attribut, und geben Sie nicht von einer GUID, die der Compiler verwendet die gleiche GUID für beide Klassen aus, und dies führt zu einem MIDL-Fehler.  Daher sollten Sie verwenden die `uuid` -Attribut bei Verwendung von **Co-Klasse**.

**ATL-Projekte**

Wenn dieses Attribut die Definition einer Klasse oder Struktur in einem ATL-Projekt steht es:

- Fügt Code oder Daten zur Unterstützung der automatischen Registrierung für das Objekt an.

- Fügt Code oder Daten zum Unterstützen von COM-Klassenfactory für das Objekt an.

- Fügt Code oder Daten implementieren `IUnknown` , und stellen Sie dem Objekt ein COM-erstellbares Objekt.

Insbesondere werden die folgenden Basisklassen des Zielobjekts hinzugefügt:

- [CComCoClass-Klasse](../../atl/reference/ccomcoclass-class.md) stellt Standard-Klasse Factory und Aggregation für das Objekt.

- [CComObjectRootEx-Klasse](../../atl/reference/ccomobjectrootex-class.md) verfügt über eine Vorlage anhand der threading Modellklasse, die gemäß der [threading](threading-cpp.md) Attribut. Wenn die `threading` Attribut nicht angegeben wird, der Standardwert threading-Modell ist Apartment.

- [IProvideClassInfo2Impl](../../atl/reference/iprovideclassinfo2impl-class.md) wird hinzugefügt, wenn die [Noncreatable](noncreatable.md) Attribut ist nicht für das Zielobjekt angegeben.

Abschließend wird jeder duale Schnittstelle, die nicht mit der eingebetteten IDL definiert ist mit dem entsprechenden ersetzt [IDispatchImpl](../../atl/reference/idispatchimpl-class.md) Klasse. Wenn die duale Schnittstelle in der eingebetteten IDL definiert ist, wird die Schnittstelle in der Basisliste nicht geändert werden.

Die **Co-Klasse** Attribut macht zudem die folgenden Funktionen verfügbar über den eingefügten Code oder im Fall von `GetObjectCLSID`, als statische Methode in der Basisklasse `CComCoClass`:

- `UpdateRegistry` registriert die Klassenfactorys der Zielklasse an.

- `GetObjectCLSID`, die Registrierung, bezieht kann auch zum Abrufen der CLSID der Zielklasse verwendet werden.

- `GetObjectFriendlyName` Standardmäßig gibt eine Zeichenfolge im Format "\<*Zielklassenname*> `Object`". Wenn diese Funktion bereits vorhanden ist, wird er nicht hinzugefügt. Fügen Sie diese Funktion auf die Zielklasse, um einen aussagekräftigeren Namen als automatisch generierte zurückzugeben.

- `GetProgID`, die Registrierung, verknüpft ist, gibt die Zeichenfolge, die mit angegebenen die [progid](progid.md) Attribut.

- `GetVersionIndependentProgID` hat die gleiche Funktion wie `GetProgID`, jedoch wird die Zeichenfolge, die mit angegebenen [Vi_progid](vi-progid.md).

Die folgenden Änderungen, die mit der COM-Zuordnung verknüpft sind, werden für die Zielklasse vorgenommen:

- Eine COM-Zuordnung wird hinzugefügt, und für alle Schnittstellen, die die Zielklasse abgeleitet und alle Einträge, die gemäß der [Einstiegspunkte für COM-Schnittstellen](../../mfc/com-interface-entry-points.md) Attribut oder die von der [Aggregate](aggregates.md) Attribut.

- Ein [OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto) Makro wird in der COM-Zuordnung eingefügt.

Der Name der Co-Klasse in der IDL-Datei für die Klasse generiert, müssen den gleichen Namen wie die Klasse.  Zum Beispiel, und verweisen auf das folgende Beispiel die Klassen-ID für eine Co-Klasse den Zugriff auf `CMyClass`, verwenden Sie in einem Client über die MIDL-generierten Headerdatei `CLSID_CMyClass`.

## <a name="example"></a>Beispiel

Der folgende Code zeigt, wie Sie mit der **Co-Klasse** Attribut:

```cpp
// cpp_attr_ref_coclass1.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];

[ object, uuid("00000000-0000-0000-0000-000000000001") ]
__interface I {
   HRESULT func();
};

[coclass, progid("MyCoClass.coclass.1"), vi_progid("MyCoClass.coclass"),
appobject, uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")]
class CMyClass : public I {};
```

Das folgende Beispiel zeigt, wie die standardmäßige Implementierung einer Funktion überschrieben, das in den mittels eingefügten Code wird die **Co-Klasse** Attribut. Weitere Informationen zum Anzeigen von eingefügtem Code finden Sie unter [/Fx](../../build/reference/fx-merge-injected-code.md) . Alle Basisklassen oder Schnittstellen, mit denen Sie für eine Klasse wird werden in den eingefügten Code angezeigt. Darüber hinaus wird, wenn eine Klasse ist standardmäßig in den eingefügten Code enthalten, und Sie explizit dieser Klasse als Basis für die Co-Klasse angeben, Attributanbieter das Formular angegeben, die in Ihrem Code verwenden.

```cpp
// cpp_attr_ref_coclass2.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlcom.h>
#include <atlwin.h>
#include <atltypes.h>
#include <atlctl.h>
#include <atlhost.h>
#include <atlplus.h>

[module(name="MyLib")];

[object, uuid("00000000-0000-0000-0000-000000000000")]
__interface bb {};

[coclass, uuid("00000000-0000-0000-0000-000000000001")]
class CMyClass : public bb {
public:
   // by adding the definition of UpdateRegistry to your code, // the function will not be included in the injected code
   static HRESULT WINAPI UpdateRegistry(BOOL bRegister) {
      // you can add to the default implementation
      CRegistryVirtualMachine rvm;
      HRESULT hr;
      if (FAILED(hr = rvm.AddStandardReplacements()))
         return hr;
      rvm.AddReplacement(_T("FriendlyName"), GetObjectFriendlyName());
      return rvm.VMUpdateRegistry(GetOpCodes(), GetOpcodeStringVals(),       GetOpcodeDWORDVals(), GetOpcodeBinaryVals(), bRegister);
   }
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**class**, **struct**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[COM-Attribute](com-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[appobject](appobject.md)
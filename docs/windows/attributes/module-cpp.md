---
title: Modul (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.module
helpviewer_keywords:
- module attributes
ms.assetid: 02223b2a-62b5-4262-832f-564b1e11e58e
ms.openlocfilehash: 5c69e0aa9e3444ec9b43470f8feb4d1f870dc9c8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409186"
---
# <a name="module-c"></a>module (C++)

Definiert den Bibliotheksblock in der IDL-Datei.

## <a name="syntax"></a>Syntax

```cpp
[ module (type=dll, name=string, version=1.0, uuid=uuid, lcid=integer, control=boolean, helpstring=string, helpstringdll=string, helpfile=string, helpcontext=integer, helpstringcontext=integer, hidden=boolean, restricted=boolean, custom=string, resource_name=string,) ];
```

### <a name="parameters"></a>Parameter

*Typ*<br/>
(Optional) Dabei kann es sich um eine der folgenden sein:

- `dll` Fügt Funktionen und Klassen, mit die die resultierende DLL als in-Process-com-Server verwendet werden können. Dies ist der Standardwert.

- `exe` Fügt Funktionen und Klassen, mit denen die resultierende ausführbare Datei als ein Out-of-Process-COM-Server-Funktion.

- `service` Fügt Funktionen und Klassen, mit denen die resultierende ausführbare Datei als ein NT-Dienst zu.

- `unspecified` Deaktiviert die Einfügung von ATL-Code im Zusammenhang mit dem Modulattribut: Einfügung der ATL-Modulklasse, globalen Instanz _AtlModule und von Einstiegspunkt zeigen Funktionen. Einfügen von ATL-Code aufgrund von anderen Attributen im Projekt wird nicht deaktiviert.

*name*<br/>
(Optional) Der Name des bibliotheksblocks.

*version*<br/>
(Optional) Die Versionsnummer, die Sie dem bibliotheksblock zuweisen möchten. Der Standardwert ist 1,0.

*uuid*<br/>
Eindeutige ID für die Bibliothek. Wenn Sie diesen Parameter weglassen, wird automatisch eine ID für die Bibliothek generiert. Müssen Sie möglicherweise Abrufen der *Uuid* des Blocks Bibliothek, die Sie mithilfe des Bezeichners können **__uuidof (** *Libraryname* **)**.

*lcid*<br/>
Der Lokalisierungsparameter. Weitere Informationen finden Sie unter [lcid](/windows/desktop/Midl/lcid) .

*Steuerelement*<br/>
(Optional) Gibt an, dass alle Co-Klassen in der Bibliothek Steuerelemente sind.

*helpstring*<br/>
Gibt die Typbibliothek an.

*helpstringdll*<br/>
(Optional) Legt den Namen der DLL-Datei zu verwenden, um eine Suche nach Dokument auszuführen. Weitere Informationen finden Sie unter [helpstringdll](/windows/desktop/Midl/helpstringdll) .

*helpfile*<br/>
(Optional) Der Name des der **Hilfe** -Datei für die Typbibliothek.

*helpcontext*<br/>
(Optional) Die **Hilfe-ID** für diese Typbibliothek.

*helpstringcontext*<br/>
(Optional) Finden Sie unter [Helpstringcontext](helpstringcontext.md) für Weitere Informationen.

*hidden*<br/>
(Optional) Verhindert, dass die gesamte Bibliothek angezeigt wird. Dies ist für die Verwendung mit Steuerelementen vorgesehen. Hosts müssen eine neue Typbibliothek erstellen, die das Steuerelement mit erweiterten Eigenschaften umschließt. Weitere Informationen finden Sie unter [hidden](/windows/desktop/Midl/hidden) MIDL-Attribut.

*restricted*<br/>
(Optional) Mitglieder der Bibliothek können nicht beliebig aufgerufen werden. Weitere Informationen finden Sie unter [restricted](/windows/desktop/Midl/restricted) MIDL-Attribut.

*custom*<br/>
(Optional) Ein oder mehrere Attribute; Dies ist vergleichbar mit der [benutzerdefinierte](custom-cpp.md) Attribut. Der erste Parameter für *benutzerdefinierte* ist die GUID des Attributs. Zum Beispiel:

```
[module(custom={guid,1}, custom={guid1,2})]
```

*resource_name*<br/>
Die Zeichenfolgenressource-ID der RGS-Datei, die verwendet wird, um die APP-ID der DLL, ausführbaren Datei oder des Diensts zu registrieren. Wenn das Modul vom Typ Dienst ist, wird dieses Argument auch verwendet, um die ID der Zeichenfolge mit dem Dienstnamen zu erhalten.

> [!NOTE]
> Die RGS-Datei und die Zeichenfolge, die den Namen des Diensts enthält, sollten den gleichen numerischen Wert enthalten.

## <a name="remarks"></a>Hinweise

Wenn Sie nicht den Parameter *restricted* auf [emitidl](emitidl.md)setzen, ist **module** in jedem Programm erforderlich, das C++-Attribute verwendet.

Ein Bibliotheksblock wird erstellt, wenn Sie zusätzlich zum **module** -Attribut im Quellcode auch [dispinterface](dispinterface.md), [dual](dual.md), [object](object-cpp.md)oder ein Attribut, das [coclass](coclass.md)impliziert, verwenden.

Pro IDL-Datei ist ein Bibliotheksblock zulässig. Mehrere Modul-Einträge im Quellcode werden zusammengeführt und die neuesten Parameterwerte werden implementiert.

Wenn dieses Attribut in einem Projekt verwendet wird, das ATL verwendet, ändert sich das Verhalten des Attributs. Zusätzlich zu den oben beschriebenen Verhalten fügt das Attribut auch ein globales Objekt (namens `_AtlModule`) mit den korrekten Typ und Code für zusätzliche Unterstützung. Wenn das Attribut eigenständig ist, wird eine von dem richtigen Modultyp abgeleitete Klasse eingefügt. Wenn das Attribut auf eine Klasse angewendet wird, wird eine Basisklasse des richtigen Modultyps hinzugefügt. Der richtige Typ wird durch den Wert bestimmt die *Typ* Parameter:

- `type` = **dll**

   [CAtlDllModuleT](../../atl/reference/catldllmodulet-class.md) dient als Basisklasse und als für einen COM-Server erforderliche Standard-DLL-Einstiegspunkte. Diese Einstiegspunkte sind [DllMain](/windows/desktop/Dlls/dllmain), [DllRegisterServer](/windows/desktop/api/olectl/nf-olectl-dllregisterserver), [DllUnRegisterServer](/windows/desktop/api/olectl/nf-olectl-dllunregisterserver), [DllCanUnloadNow](/windows/desktop/api/combaseapi/nf-combaseapi-dllcanunloadnow)und [DllGetClassObject](https://msdn.microsoft.com/library/windows/desktop/dd797891).

- `type` = **exe**

   [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md) dient als Basisklasse und ausführbarer Standardeinstiegspunkt [WinMain](/windows/desktop/api/winbase/nf-winbase-winmain).

- `type` = **service**

   [CAtlServiceModuleT](../../atl/reference/catlservicemodulet-class.md) dient als Basisklasse und ausführbarer Standardeinstiegspunkt [WinMain](/windows/desktop/api/winbase/nf-winbase-winmain).

- `type` = **unspecified**

   Deaktiviert die Einfügung von ATL-Code im Zusammenhang mit dem Modulattribut.

## <a name="example"></a>Beispiel

Der folgende Code zeigt, wie ein Bibliotheksblock in der generierten IDL-Datei erstellt wird.

```cpp
// cpp_attr_ref_module1.cpp
// compile with: /LD
[module(name="MyLibrary", version="1.2", helpfile="MyHelpFile")];
```

Der folgende Code zeigt, dass Sie Ihre eigene Implementierung einer Funktion angeben können, die in dem Code angezeigt wird, der durch die Verwendung von **module**eingefügt wurde. Weitere Informationen zum Anzeigen von eingefügtem Code finden Sie unter [/Fx](../../build/reference/fx-merge-injected-code.md) . Um eine der Funktionen zu überschreiben, die vom Attribut **module** eingefügt wurden, erstellen Sie eine Klasse, die die Implementierung der Funktion enthält, und wenden Sie das Attribut **module** auf diese Klasse an.

```cpp
// cpp_attr_ref_module2.cpp
// compile with: /LD /link /OPT:NOREF
#include <atlbase.h>
#include <atlcom.h>
#include <atlwin.h>
#include <atltypes.h>
#include <atlctl.h>
#include <atlhost.h>
#include <atlplus.h>

// no semicolon after attribute block
[module(dll, name="MyLibrary", version="1.2", helpfile="MyHelpFile")]
// module attribute now applies to this class
class CMyClass {
public:
BOOL WINAPI DllMain(DWORD dwReason, LPVOID lpReserved) {
   // add your own code here
   return __super::DllMain(dwReason, lpReserved);
   }
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Überall|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[Eigenständige Attribute](stand-alone-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[usesgetlasterror](usesgetlasterror.md)<br/>
[library](/windows/desktop/Midl/library)<br/>
[helpcontext](helpcontext.md)<br/>
[helpstring](helpstring.md)<br/>
[helpfile](helpfile.md)<br/>
[version](version-cpp.md)
---
title: Idl_module (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.idl_module
helpviewer_keywords:
- idl_module attribute
ms.assetid: 3578b337-e38a-4334-b747-15404c02dbc0
ms.openlocfilehash: 80e4909a61b5b53ecde19471f2c838dd4c425874
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409459"
---
# <a name="idlmodule"></a>idl_module

Gibt einen Einstiegspunkt in eine DLL-Datei an.

## <a name="syntax"></a>Syntax

```cpp
[ idl_module (name=module_name, dllname=dll, uuid="uuid", helpstring="help text", helpstringcontext=helpcontextID, helpcontext=helpcontext, hidden, restricted) ]
function declaration
```

### <a name="parameters"></a>Parameter

*name*<br/>
Ein benutzerdefinierter Name für den Codeblock, der in der IDL-Datei angezeigt wird.

*dllname*<br/>
(Optional) Die DLL-Datei, die den Export enthält.

*uuid*<br/>
(Optional) Eine eindeutige ID.

*helpstring*<br/>
(Optional) Eine Zeichenfolge, die die Typbibliothek beschrieben wird.

*helpstringcontext*<br/>
(Optional) Die ID eines Hilfethemas in eine .hlp oder CHM-Datei.

*helpcontext*<br/>
(Optional) Die Hilfe-ID für diese Typbibliothek.

*hidden*<br/>
(Optional) Ein Parameter, der verhindert, dass die Bibliothek angezeigt wird. Weitere Informationen finden Sie unter [hidden](/windows/desktop/Midl/hidden) MIDL-Attribut.

*restricted*<br/>
(Optional) Mitglieder der Bibliothek können nicht beliebig aufgerufen werden. Weitere Informationen finden Sie unter [restricted](/windows/desktop/Midl/restricted) MIDL-Attribut.

*Funktionsdeklaration*<br/>
Die Funktion, die Sie definieren.

## <a name="remarks"></a>Hinweise

Die **Idl_module** C++ Attribut können Sie den Einstiegspunkt in einer DLL-Datei angeben, dem Sie Daten aus einer DLL-Datei importieren können.

Die **Idl_module** Attribut hat ähnliche Funktionen wie die [Modul](/windows/desktop/Midl/module) MIDL-Attribut.

Sie können alles von einer COM-Objekt exportieren, die Sie aus einer DLL-Datei exportieren können, indem Sie einen DLL-Einstiegspunkt in den bibliotheksblock einer IDL-Datei einfügen.

Ihre müssen **Idl_module** in zwei Schritten. Zunächst müssen Sie ein Paar aus Name/DLL definieren. Klicken Sie dann bei Verwendung von **Idl_module** um ein Einstiegspunkt anzugeben, geben Sie den Namen und alle zusätzlichen Attribute.

## <a name="example"></a>Beispiel

Der folgende Code zeigt, wie Sie mit der **Idl_module** Attribut:

```cpp
// cpp_attr_ref_idl_module.cpp
// compile with: /LD
[idl_quote("midl_pragma warning(disable:2461)")];
[module(name="MyLibrary"), idl_module(name="MyLib", dllname="xxx.dll")];
[idl_module(name="MyLib"), entry(4), usesgetlasterror]
void FuncName(int i);
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
[Eigenständige Attribute](stand-alone-attributes.md)<br/>
[entry](entry.md)
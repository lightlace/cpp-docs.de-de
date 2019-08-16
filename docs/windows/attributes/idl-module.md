---
title: idl_module (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.idl_module
helpviewer_keywords:
- idl_module attribute
ms.assetid: 3578b337-e38a-4334-b747-15404c02dbc0
ms.openlocfilehash: 8838a833552ae7066dbcf17b4f676d6626c069f8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514673"
---
# <a name="idl_module"></a>idl_module

Gibt einen Einstiegspunkt in einer DLL-Datei an.

## <a name="syntax"></a>Syntax

```cpp
[ idl_module (name=module_name, dllname=dll, uuid="uuid", helpstring="help text", helpstringcontext=helpcontextID, helpcontext=helpcontext, hidden, restricted) ]
function declaration
```

### <a name="parameters"></a>Parameter

*name*<br/>
Ein benutzerdefinierter Name für den Codeblock, der in der IDL-Datei angezeigt wird.

*dllname*<br/>
Optionale Die DLL-Datei, die den Export enthält.

*uuid*<br/>
Optionale Eine eindeutige ID.

*helpstring*<br/>
Optionale Eine Zeichenfolge, mit der die Typbibliothek beschrieben wird.

*helpstringcontext*<br/>
Optionale Die ID eines Hilfe Themas in einer. hlp-oder CHM-Datei.

*helpcontext*<br/>
Optionale Die Hilfe-ID für diese Typbibliothek.

*hidden*<br/>
Optionale Ein-Parameter, der verhindert, dass die Bibliothek angezeigt wird. Weitere Informationen finden Sie unter [hidden](/windows/win32/Midl/hidden) MIDL-Attribut.

*restricted*<br/>
Optionale Member der Bibliothek können nicht willkürlich aufgerufen werden. Weitere Informationen finden Sie unter [restricted](/windows/win32/Midl/restricted) MIDL-Attribut.

*Funktionsdeklaration*<br/>
Die Funktion, die Sie definieren.

## <a name="remarks"></a>Hinweise

Mit dem **idl_module** C++ -Attribut können Sie den Einstiegspunkt in einer DLL-Datei angeben, die es Ihnen ermöglicht, aus einer DLL-Datei zu importieren.

Das **idl_module** -Attribut verfügt über eine ähnliche Funktionalität wie das- [Modul](/windows/win32/Midl/module) -Mittel l-Attribut.

Sie können beliebige Elemente aus einem COM-Objekt exportieren, das Sie aus einer DLL-Datei exportieren können, indem Sie einen DLL-Einstiegspunkt in den Bibliotheks Block einer IDL-Datei einfügen.

Ihr muss **idl_module** in zwei Schritten verwenden. Zunächst müssen Sie ein Name-DLL-Paar definieren. Wenn Sie dann **idl_module** verwenden, um einen Einstiegspunkt anzugeben, geben Sie den Namen und alle zusätzlichen Attribute an.

## <a name="example"></a>Beispiel

Der folgende Code zeigt, wie das **idl_module** -Attribut verwendet wird:

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
|**Erforderliche Attribute**|None|
|**Ungültige Attribute**|None|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Eigenständige Attribute](stand-alone-attributes.md)<br/>
[entry](entry.md)
---
title: Idl_module | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.idl_module
dev_langs:
- C++
helpviewer_keywords:
- idl_module attribute
ms.assetid: 3578b337-e38a-4334-b747-15404c02dbc0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 73047962daf32eae6c01bb0ea6f6688a83e19402
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715532"
---
# <a name="idlmodule"></a>idl_module

Gibt einen Einstiegspunkt in eine DLL-Datei an.

## <a name="syntax"></a>Syntax

```cpp
[ idl_module (
   name=module_name,
   dllname=dll,
   uuid="uuid",
   helpstring="help text",
   helpstringcontext=helpcontextID,
   helpcontext=helpcontext,
   hidden,
   restricted
) ]
function declaration
```

### <a name="parameters"></a>Parameter

*name*  
Ein benutzerdefinierter Name für den Codeblock, der in der IDL-Datei angezeigt wird.

*DLL-Name*  
(Optional) Die DLL-Datei, die den Export enthält.

*uuid*  
(Optional) Eine eindeutige ID.

*helpstring*  
(Optional) Eine Zeichenfolge, die die Typbibliothek beschrieben wird.

*helpstringcontext*  
(Optional) Die ID eines Hilfethemas in eine .hlp oder CHM-Datei.

*helpcontext*  
(Optional) Die Hilfe-ID für diese Typbibliothek.

*hidden*  
(Optional) Ein Parameter, der verhindert, dass die Bibliothek angezeigt wird. Finden Sie unter den [ausgeblendeten](/windows/desktop/Midl/hidden) MIDL-Attribut für Weitere Informationen.

*restricted*  
(Optional) Mitglieder der Bibliothek können nicht beliebig aufgerufen werden. Finden Sie unter den [eingeschränkten](/windows/desktop/Midl/restricted) MIDL-Attribut für Weitere Informationen.

*Funktionsdeklaration*  
Die Funktion, die Sie definieren.

## <a name="remarks"></a>Hinweise

Die **Idl_module** C++-Attribut ermöglicht die Angabe den Einstiegspunkt in eine DLL-Datei, dem Sie Daten aus einer DLL-Datei importieren können.

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

Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  
[Eigenständige Attribute](../windows/stand-alone-attributes.md)  
[entry](../windows/entry.md)  
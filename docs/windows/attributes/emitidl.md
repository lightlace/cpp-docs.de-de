---
title: Emitidl (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.emitidl
dev_langs:
- C++
helpviewer_keywords:
- emitidl attribute
ms.assetid: 85b80c56-578e-4392-ac03-8443c74ebb7d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5e11e1ce061fcf2e9ce21155dcbeb93b45b66238
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791739"
---
# <a name="emitidl"></a>emitidl

Gibt an, ob alle nachfolgenden IDL-Attribute verarbeitet und in der generierten IDL-Datei platziert werden.

## <a name="syntax"></a>Syntax

```cpp
[ emitidl(state, defaultimports=boolean) ];
```

### <a name="parameters"></a>Parameter

*state*<br/>
Einen der folgenden Werte möglich: `true`, `false`, `forced`, `restricted`, `push`, oder `pop`.

- Wenn `true`, die IDL-Attribute, Kategorie bei der eine Quellcodedatei in der generierten IDL-Datei platziert werden. Dies ist die Standardeinstellung für **Emitidl**.

- Wenn `false`, die IDL-Attribute, Kategorie in einer Quellcodedatei festgestellt werden nicht in der generierten IDL-Datei abgelegt.

- Wenn `restricted`, können Sie die IDL-Attribute, die in der Datei ohne muss eine [Modul](module-cpp.md) Attribut. Der Compiler erzeugt eine IDL-Datei nicht.

- Wenn `forced`, überschreibt eine nachfolgende `restricted` -Attribut, das eine Datei haben muss eine `module` Attribut treten IDL-Attribute in der Datei.

- `push` ermöglicht Ihnen das Speichern Sie die aktuelle **Emitidl** Einstellungen, die ein internes **Emitidl** -Stapel und `pop` ermöglicht Ihnen das Festlegen **Emitidl** an einen beliebigen Wert am Anfang der internen **Emitidl** Stapel.

`defaultimports=`*boolesche* \(optional)  
- Wenn *booleschen* ist **"true"**, docobj.idl in der generierten IDL-Datei importiert wird. Auch wenn es sich bei eine IDL-Datei mit dem gleichen Namen wie ein h, die Sie `#include` in Ihrer Quelle Code finden Sie im gleichen Verzeichnis wie der h-Datei, und klicken Sie dann die generierten IDL-Datei enthält eine Import-Anweisung für diese IDL-Datei.

- Wenn *booleschen* ist **"false"**, docobj.idl nicht in der generierten IDL-Datei importiert. Sie müssen explizit importieren IDL-Dateien mit [importieren](import.md).

## <a name="remarks"></a>Hinweise

Nach der **Emitidl** C++-Attribut in einer Quellcodedatei festgestellt wird, Kategorie IDL-Attribute werden in der generierten IDL-Datei platziert. Es ist keine **Emitidl** IDL-Attribute in der Quelldatei für die Code-Attribut werden in der generierten IDL-Datei ausgegeben.

Es ist möglich, mehrere **Emitidl** Attribute in einer Quellcodedatei. Wenn `[emitidl(false)];` gefunden wird in eine Datei ohne eine nachfolgende `[emitidl(true)];`, und klicken Sie dann keine Attribute in der generierten IDL-Datei verarbeitet werden.

Jedes Mal, die der Compiler eine neue Datei findet **Emitidl** wird implizit festgelegt, **"true"**.

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

[Compilerattribute](compiler-attributes.md)<br/>
[Eigenständige Attribute](stand-alone-attributes.md)  

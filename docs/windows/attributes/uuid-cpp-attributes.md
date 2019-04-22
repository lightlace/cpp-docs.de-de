---
title: uuid (C++-Attribute)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.uuid
helpviewer_keywords:
- uuid attribute
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
ms.openlocfilehash: 8d9d55fc2a340165480cab4036ad1e5323e6b625
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026041"
---
# <a name="uuid-c-attributes"></a>uuid (C++-Attribute)

Gibt die eindeutige ID für eine Klasse oder Schnittstelle an.

## <a name="syntax"></a>Syntax

```cpp
[ uuid(
   "uuid"
) ]
```

### <a name="parameters"></a>Parameter

*uuid*<br/>
Ein 128-Bit, eindeutigen Bezeichner.

## <a name="remarks"></a>Hinweise

Wenn die Definition einer Schnittstelle oder Klasse nicht angegeben ist die **Uuid** C++-Attribut, und klicken Sie dann auf Visual C++-Compiler bietet eine. Bei Angabe einer **Uuid**, Sie müssen die Anführungszeichen einschließen.

Wenn Sie keinen angeben **Uuid**, generiert der Compiler die gleiche GUID für die Schnittstellen oder Klassen mit dem gleichen Namen in anderen Attributs Projekte auf einem Computer.

Sie können Uuidgen.exe oder Guidgen.exe verwenden, um Ihren eigenen eindeutigen IDs zu generieren. (Klicken Sie zum Ausführen eines dieser Tools auf **starten** , und klicken Sie auf **ausführen** im Menü. Geben Sie den Namen des Tools erforderlich.)

Wenn in einem Projekt verwendet, die nicht auch ATL verwendet, Angeben der **Uuid** Attribut entspricht der Angabe der [Uuid](../../cpp/uuid-cpp.md) **__declspec** Modifizierer. Zum Abrufen der **Uuid** einer Klasse, können Sie [__uuidof](../../cpp/uuidof-operator.md)

## <a name="example"></a>Beispiel

Finden Sie unter den [bindbare](bindable.md) Beispiel für ein Beispiel für die Verwendung von **Uuid**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**class**, **struct**, **interface**, **union**, **enum**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Schnittstellenattribut](interface-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[uuid](/windows/desktop/Midl/uuid)
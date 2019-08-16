---
title: uuid (C++-Attribute)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.uuid
helpviewer_keywords:
- uuid attribute
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
ms.openlocfilehash: d644f59ac92bf4e39f191c291dd4fef626411c3d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514949"
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
Ein eindeutiger 128-Bit-Bezeichner.

## <a name="remarks"></a>Hinweise

Wenn die Definition einer Schnittstelle oder Klasse das **UUID** C++ -Attribut nicht angibt, wird vom Microsoft C++ -Compiler eine bereitgestellt. Wenn Sie eine **UUID**angeben, müssen Sie die Anführungszeichen einschließen.

Wenn Sie **UUID**nicht angeben, generiert der Compiler dieselbe GUID für Schnittstellen oder Klassen mit demselben Namen in unterschiedlichen Attribut Projekten auf einem Computer.

Sie können "uuidgen. exe" oder "Guidgen. exe" verwenden, um eigene eindeutige IDs zu generieren. (Um eines dieser Tools auszuführen, klicken Sie auf **Start** , und klicken Sie im Menü auf **Ausführen** . Geben Sie dann den Namen des erforderlichen Tools ein.)

Wenn Sie in einem Projekt verwendet wird, das nicht auch ATL verwendet, ist das Angeben des **UUID** -Attributs mit dem Angeben des [UUID](../../cpp/uuid-cpp.md) **__declspec** -Modifizierers identisch. Zum Abrufen der **UUID** einer Klasse können Sie [__uuidof](../../cpp/uuidof-operator.md) verwenden.

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von **UUID**finden Sie im [bindbare](bindable.md) -Beispiel.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**, **Schnittstelle**, **Union**, Enumeration|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|None|
|**Ungültige Attribute**|None|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Schnittstellenattribut](interface-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[uuid](/windows/win32/Midl/uuid)
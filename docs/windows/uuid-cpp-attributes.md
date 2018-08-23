---
title: UUID (C++-Attribute) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.uuid
dev_langs:
- C++
helpviewer_keywords:
- uuid attribute
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8d18b323b255c8549ae275d3e6b88471f134c8b4
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42606779"
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

*uuid*  
Ein 128-Bit, eindeutigen Bezeichner.

## <a name="remarks"></a>Hinweise

Wenn die Definition einer Schnittstelle oder Klasse nicht angegeben ist die **Uuid** C++-Attribut, und klicken Sie dann auf Visual C++-Compiler bietet eine. Bei Angabe einer **Uuid**, Sie müssen die Anführungszeichen einschließen.

Wenn Sie keinen angeben **Uuid**, generiert der Compiler die gleiche GUID für die Schnittstellen oder Klassen mit dem gleichen Namen in anderen Attributs Projekte auf einem Computer.

Sie können Uuidgen.exe oder Guidgen.exe verwenden, um Ihren eigenen eindeutigen IDs zu generieren. (Klicken Sie zum Ausführen eines dieser Tools auf **starten** , und klicken Sie auf **ausführen** im Menü. Geben Sie den Namen des Tools erforderlich.)

Wenn in einem Projekt verwendet, die nicht auch ATL verwendet, Angeben der **Uuid** Attribut entspricht der Angabe der [Uuid](../cpp/uuid-cpp.md) **__declspec** Modifizierer. Zum Abrufen der **Uuid** einer Klasse, können Sie [__uuidof](../cpp/uuidof-operator.md)

## <a name="example"></a>Beispiel

Finden Sie unter den [bindbare](../windows/bindable.md) Beispiel für ein Beispiel für die Verwendung von **Uuid**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**, **Schnittstelle**, **Union**, **Enumeration**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  
[Schnittstellenattribut](../windows/interface-attributes.md)  
[Klassenattribute](../windows/class-attributes.md)  
[typedef-, enum-, union- und struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)  
[uuid](http://msdn.microsoft.com/library/windows/desktop/aa367302)  